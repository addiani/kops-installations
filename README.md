# kubectl installation for Centos
-cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOF
-yum install -y kubectl
  
  # kubectl for mac
  
- curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-  release/release/stable.txt)/bin/linux/amd64/kubectl
# To download a specific version, replace the $(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt) portion of the command with the specific version.

# For example, to download version v1.13.0 on macOS, type:
# curl-LO https://storage.googleapis.com/kubernetes-release/release/v1.13.0/bin/darwin/amd64/kubectl
-chmod +x ./kubectl
-sudo mv ./kubectl /usr/local/bin/kubectl
- kubectl completion -h   
# kubectl completion bash > $(brew --prefix)/etc/bash_completion.d/kubectl   # autocompletion for mac manually 

# kubectl on linux
- curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
# for specific version replace=  $(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)
# curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.13.0/bin/linux/amd64/kubectl
- chmod +x ./kubectl
# Move the binary in to your PATH.

- sudo mv ./kubectl /usr/local/bin/kubectl
# autocompletion
-yum install bash-completion -y
- source <(kubectl completion bash)
- echo "source <(kubectl completion bash)" >> ~/.bashrc

