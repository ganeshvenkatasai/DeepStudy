# DevOps
---
## Linux Commands
- `ls` → List files and directories
- `ls -l` → Long listing format (permissions, owner, size, date)
- `ls -a` → Show hidden files
- `pwd` → Print working directory
- `cd <dir>` → Change directory
- `cd ..` → Go up one directory
- `mkdir <dir>` → Create directory
- `rmdir <dir>` → Remove empty directory
- `rm -r <dir>` → Remove directory recursively
- `touch <file>` → Create empty file / update timestamp
- `cp <src> <dest>` → Copy file
- `cp -r <src> <dest>` → Copy directory recursively
- `mv <src> <dest>` → Move / Rename file
- `rm <file>` → Remove file
- `find <path> -name "<pattern>"` → Find files by name
- `tree` → Show directory structure in tree format
- `cat <file>` → View file content
- `tac <file>` → View file in reverse
- `less <file>` → View large files page by page
- `head <file>` → Show first 10 lines
- `tail <file>` → Show last 10 lines
- `tail -f <file>` → Follow log file in real-time
- `nano <file>` → Edit file (simple editor)
- `vi <file>` / `vim <file>` → Open file in vi/vim editor
- `ls -l` → Show file permissions
- `chmod 755 <file>` → Change file permissions
- `chmod +x <file>` → Make file executable
- `chown user:group <file>` → Change ownership
- `chgrp <group> <file>` → Change group ownership
- `umask` → Show default permission mask
- `tar -cvf archive.tar file1 file2` → Create tar archive
- `tar -xvf archive.tar` → Extract tar archive
- `tar -czvf archive.tar.gz dir/` → Create compressed archive
- `tar -xzvf archive.tar.gz` → Extract compressed archive
- `gzip <file>` → Compress file
- `gunzip <file.gz>` → Decompress file
- `zip archive.zip file1 file2` → Create zip archive
- `unzip archive.zip` → Extract zip archive
- `ps` → Show running processes
- `ps aux` → Detailed process list
- `top` → Show running processes with usage
- `htop` → Interactive process monitor
- `kill <pid>` → Kill process by PID
- `kill -9 <pid>` → Force kill process
- `pkill <name>` → Kill process by name
- `jobs` → Show background jobs
- `bg %1` → Resume job in background
- `fg %1` → Resume job in foreground
- `ifconfig` / `ip a` → Show network interfaces
- `ping <host>` → Check connectivity
- `curl <url>` → Fetch data from URL
- `wget <url>` → Download file
- `scp <src> user@host:/path` → Secure copy to remote
- `scp user@host:/path/file .` → Copy file from remote
- `rsync -avz src/ dest/` → Sync files efficiently
- `netstat -tulnp` → Show listening ports
- `ss -tulnp` → Modern alternative to netstat
- `ssh user@host` → Connect to remote server
- `telnet <host> <port>` → Test connectivity to port
- `traceroute <host>` → Show route packets take
- `whoami` → Current user
- `who` → Show logged-in users
- `id` → Show UID, GID, groups
- `adduser <name>` → Add user
- `passwd <user>` → Change password
- `su - <user>` → Switch user
- `sudo <command>` → Run as superuser
- `groups <user>` → Show groups of user
- `df -h` → Disk usage (human-readable)
- `du -sh <dir>` → Directory size
- `free -h` → Memory usage
- `uptime` → System uptime and load
- `dmesg` → Kernel boot messages
- `iostat` → CPU and I/O stats
- `vmstat` → Virtual memory stats
- `sar` → System activity report
- `lsof -i :<port>` → List process using a port
- `apt update` → Update package index
- `apt upgrade` → Upgrade packages
- `apt install <pkg>` → Install package
- `apt remove <pkg>` → Remove package
- `dpkg -i <pkg.deb>` → Install .deb package
- `yum install <pkg>` → Install package
- `yum remove <pkg>` → Remove package
- `dnf update` → Update system
- `grep "pattern" file` → Search inside file
- `grep -r "pattern" dir/` → Recursive search
- `grep -i "pattern" file` → Case-insensitive search
- `awk '{print $1}' file` → Print first column
- `sed 's/foo/bar/g' file` → Replace text in file
- `sort file` → Sort file
- `uniq file` → Remove duplicates
- `wc -l file` → Count lines
- `cut -d',' -f1 file.csv` → Cut first column (CSV)
- `uname -a` → Kernel and system info
- `hostname` → Show hostname
- `uptime` → System uptime
- `cat /etc/os-release` → OS version
- `lscpu` → CPU info
- `lsblk` → List block devices
- `lspci` → List PCI devices
- `lsusb` → List USB devices
- `journalctl -xe` → View system logs
- `dmesg | less` → Kernel logs
- `tail -f /var/log/syslog` → Follow system log
- `tail -f /var/log/messages` → Follow system messages
- `alias ll='ls -la'` → Create alias
- `history` → Show command history
- `clear` → Clear terminal
- `date` → Show current date/time
- `cal` → Show calendar
- `echo "Hello"` → Print text
- `export VAR=value` → Set environment variable
- `env` → Show environment variables
- `crontab -e` → Edit cron jobs
- `grep "pattern" file` → Search for "pattern" in file  
- `grep -i "pattern" file` → Case-insensitive search  
- `grep -r "pattern" dir/` → Search recursively in directory  
- `grep -v "pattern" file` → Show lines NOT matching pattern  
- `grep -n "pattern" file` → Show matching line numbers  
- `grep -c "pattern" file` → Count matching lines  
- `grep -A 3 "pattern" file` → Show match + 3 lines **after**  
- `grep -B 3 "pattern" file` → Show match + 3 lines **before**  
- `grep -E "pat1|pat2" file` → Match multiple patterns (OR)  
- `grep -w "word" file` → Match exact word  
- `awk '{print $1}' file` → Print first column  
- `awk '{print $1, $3}' file` → Print multiple columns  
- `awk -F',' '{print $2}' file.csv` → Use comma as delimiter  
- `awk '/pattern/ {print $0}' file` → Print lines matching pattern  
- `awk 'NR==1' file` → Print first line  
- `awk 'NR==1,NR==5' file` → Print lines 1 to 5  
- `awk '{sum+=$1} END {print sum}' file` → Sum first column  
- `awk '{if($3 > 50) print $0}' file` → Print rows where 3rd column > 50  
- `awk 'BEGIN {FS=":"} {print $1}' /etc/passwd` → Print first field of passwd file  
- `awk 'BEGIN {OFS=","} {print $1,$2}' file` → Change output delimiter  
- `sed 's/foo/bar/' file` → Replace first "foo" with "bar" in each line  
- `sed 's/foo/bar/g' file` → Replace all "foo" with "bar"  
- `sed -n '5p' file` → Print only line 5  
- `sed -n '1,5p' file` → Print lines 1 to 5  
- `sed '/pattern/d' file` → Delete lines matching pattern  
- `sed '2d' file` → Delete line 2  
- `sed 's/[0-9]//g' file` → Remove all numbers  
- `sed -i 's/foo/bar/g' file` → Replace text **in-place**  
- `sed 's/^/prefix_/' file` → Add prefix to each line  
- `sed 's/$/_suffix/' file` → Add suffix to each line  

---

## Shell Scripting
```bash
#!/bin/bash
echo "Hello, World!"
```

```bash
name="Ganesh"
age=25
echo "Name: $name, Age: $age"
```

```bash
num=10
if [ $num -gt 5 ]; then
    echo "Greater than 5"
elif [ $num -eq 5 ]; then
    echo "Equal to 5"
else
    echo "Less than 5"
fi
```
```bash
echo "Enter choice (y/n): "
read choice
case $choice in
    y|Y) echo "Yes";;
    n|N) echo "No";;
    *) echo "Invalid";;
esac
```
```bash
for i in {1..5}; do
    echo "Count: $i"
done
```
```bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    count=$((count+1))
done
```
```bash
num=1
until [ $num -gt 5 ]; do
    echo "Number: $num"
    num=$((num+1))
done
```
```bash
greet() {
    echo "Hello, $1"
}
greet "Ganesh"
```
```bash
echo "Script name: $0"
echo "First arg: $1"
echo "All args: $@"
echo "Arg count: $#"
```
```bash
echo "Enter your name: "
read name
echo "Hello, $name!"
```
```bash
fruits=("apple" "banana" "cherry")
echo "First: ${fruits[0]}"
echo "All: ${fruits[@]}"
for fruit in "${fruits[@]}"; do
    echo "Fruit: $fruit"
done
```
- `-eq` (equal)
- `-ne` (not equal)
- `-gt` (greater than)
- `-ge` (greater or equal)
- `-lt` (less than)
- `-le` (less or equal)
- `=` (equal)
- `!=` (not equal)
- `<` (less in ASCII)
- `>` (greater in ASCII)
- `-z` (empty string)
- `-n` (non-empty string)
- `-e file` (exists)
- `-f file` (regular file)
- `-d dir` (directory)
- `-r file` (readable)
- `-w file` (writable)
- `-x file` (executable)
- `-s file` (not empty)
- `!` (NOT)
- `-a` (AND)
- `-o` (OR)
- `&&` (AND, with [[ ]])
- `||` (OR, with [[ ]])
```bash
a=10; b=5
echo "Sum: $((a+b))"
echo "Product: $((a*b))"
```
```bash
ls /home
echo $?   # 0 = success, non-zero = failure
```
```bash
file="test.txt"
if [ -f "$file" ]; then
    echo "File exists"
else
    echo "File missing"
fi
```

## Jenkins

- **Declarative Pipeline** → Simple, structured.
- **Scripted Pipeline** → More flexible, Groovy-based.
- **Job/Project** → Unit of execution.
- **Node/Agent** → Machine where job runs.
- **Executor** → Slot for executing builds.
- **Workspace** → Directory on agent where job runs.
- **SCM** → Source Code Management (Git).
- **Triggers** → Define when pipeline runs (push, cron).
- **Build Triggers**: Poll SCM, Webhooks, Scheduled builds.
- **Artifacts**: Files generated during build (e.g., `.jar`).
- **Parameters**: User inputs for jobs.
- **Credentials**: Store secrets securely.
- **Distributed Builds**: Master-Agent architecture.
## Jenkins file

```groovy
pipeline {
    agent any

    options {
        timestamps()
        buildDiscarder(logRotator(numToKeepStr: '10'))
        disableConcurrentBuilds()
    }

    environment {
        AWS_REGION   = "ap-south-1"
        APP_NAME     = "myapp"
        ECR_REPO     = "123456789012.dkr.ecr.ap-south-1.amazonaws.com/${APP_NAME}"
        IMAGE_TAG    = "v${BUILD_NUMBER}"
        DOCKER_IMAGE = "${ECR_REPO}:${IMAGE_TAG}"

        KUBE_CONFIG  = credentials('kubeconfig-cred')
        ANSIBLE_HOSTS = "/etc/ansible/hosts"
    }

    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Git branch to build')
        choice(name: 'ENV', choices: ['dev', 'staging', 'prod'], description: 'Deployment environment')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Run tests?')
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: "${params.BRANCH}", url: 'https://github.com/your-org/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Test') {
            when {
                expression { params.RUN_TESTS == true }
            }
            steps {
                sh 'mvn test'
            }
        }

        stage('Docker Build & Push to ECR') {
            steps {
                script {
                    sh """
                        aws ecr get-login-password --region ${AWS_REGION} | docker login --username AWS --password-stdin ${ECR_REPO}
                        docker build -t ${DOCKER_IMAGE} .
                        docker push ${DOCKER_IMAGE}
                    """
                }
            }
        }

        stage('Ansible Configuration') {
            steps {
                sh 'ansible-playbook -i ${ANSIBLE_HOSTS} playbooks/setup.yml'
            }
        }

        stage('Terraform Infra Provisioning (EKS)') {
            steps {
                dir('infra/terraform') {
                    sh '''
                        terraform init
                        terraform plan -out=tfplan
                        terraform apply -auto-approve tfplan
                    '''
                }
            }
        }

        stage('Configure kubeconfig') {
            steps {
                sh '''
                    aws eks update-kubeconfig --region ${AWS_REGION} --name my-eks-cluster --kubeconfig $WORKSPACE/kubeconfig
                '''
            }
        }

        stage('Kubernetes Deployment') {
            steps {
                withCredentials([file(credentialsId: 'kubeconfig-cred', variable: 'KUBECONFIG')]) {
                    sh '''
                        kubectl apply -f k8s/deployment.yaml
                        kubectl apply -f k8s/service.yaml
                        kubectl set image deployment/myapp-deployment myapp-container=${DOCKER_IMAGE}
                        kubectl rollout status deployment/myapp-deployment
                    '''
                }
            }
        }

        stage('Deploy to Environment') {
            steps {
                script {
                    if (params.ENV == 'dev') {
                        sh './deploy-dev.sh'
                    } else if (params.ENV == 'staging') {
                        sh './deploy-staging.sh'
                    } else {
                        input message: "Approve Prod Deployment?"
                        sh './deploy-prod.sh'
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
        always {
            cleanWs()
        }
    }
}

```

---

## Flow Overview
1. **Checkout** → Pulls the code from GitHub (main or param branch).  

2. **Build** → Uses Maven to build JAR.  

3. **Test** → Runs tests if `RUN_TESTS` is true.  

4. **Docker Build & Push** → Builds app Docker image & pushes to AWS ECR.  

5. **Ansible Setup** → Runs playbook (`playbooks/setup.yml`) to configure environment  
   (e.g. installing kubectl, setting AWS config, preparing cluster tools).  

6. **Terraform Apply** → Provisions AWS EKS cluster & nodes from `infra/terraform/` files.  

7. **Configure kubeconfig** → Sets Jenkins to use the new AWS EKS cluster (`aws eks update-kubeconfig`).  

8. **Kubernetes Deployment**  
   → Applies `k8s/deployment.yaml` and `k8s/service.yaml`.  
   → Updates image tag & rolls out deployment.  

9. **Deploy to ENV**  
   - **Dev** → Auto deploy.  
   - **Staging** → Deploy if branch = `staging`.  
   - **Prod** → Requires manual approval step before deploying.  

10. **Post Actions**  
    - Cleans workspace.  
    - Sends success/failure status to Jenkins dashboard.  

---
## Keywords

- `pipeline {}` → Defines the Jenkins pipeline.
- `agent any` → Runs pipeline on any available agent.
- `agent { label 'my-node' }` → Runs pipeline on a specific node/agent.
- `stages {}` → Groups multiple stages.
- `stage('name') {}` → Defines a single stage in the pipeline.
- `steps {}` → Contains steps to execute inside a stage.
- `script {}` → Runs Groovy script block inside pipeline.
- `environment {}` → Defines environment variables for pipeline/stages.
- `tools {}` → Declares tools (e.g., Maven, JDK) for pipeline.
- `options {}` → Defines pipeline options (e.g., timeout, retry).
- `parameters {}` → Defines input parameters for pipeline.
- `triggers {}` → Defines triggers (e.g., pollSCM, cron).
- `post {}` → Defines post-build actions (always, success, failure).
- `when {}` → Adds conditions for running a stage.
- `input {}` → Manual approval step in pipeline.
- `timeout(time: 5, unit: 'MINUTES')` → Aborts step/stage after given time.
- `retry(n)` → Retries a block `n` times if it fails.
- `parallel {}` → Runs stages in parallel.
- `node {}` → Allocates an executor on a node (scripted pipeline).
- `echo 'msg'` → Prints message to console.
- `sh 'command'` → Executes shell command.
- `bat 'command'` → Executes Windows batch command.
- `checkout scm` → Checks out source code from SCM.
- `git 'repo-url'` → Clones a Git repository.
- `withEnv(["VAR=value"]) {}` → Temporarily sets environment variable.
- `withCredentials {}` → Binds Jenkins credentials inside block.
- `archiveArtifacts 'path/**'` → Archives build artifacts.
- `junit 'reports/*.xml'` → Publishes JUnit test results.
- `stash` / `unstash` → Saves/restores files across stages.
- `error 'msg'` → Fails the build with error message.
- `currentBuild.result = 'SUCCESS'` → Sets build result.
- `currentBuild.result = 'FAILURE'` → Marks build as failed.
- `currentBuild.description = "text"` → Adds description to build.

---

## Ansible

---

## Terraform

---

## Applications

---