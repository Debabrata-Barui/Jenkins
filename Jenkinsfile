pipeline{
    agent any
    stages{
        stage("Install Httpd Server"){
            steps{
                sh '''
                sudo yum install httpd -y
                systemctl start httpd
                systemctl enable httpd
                '''
            }
        }
        
        stage("Install Git"){
            steps{
                sh '''
                sudo yum install git -y
                '''
            }
        }
        
        
        stage("Download From GitHub"){
            steps{
                sh '''
                cd /home/ec2-user/
                git clone https://github.com/Debabrata-Barui/WebSite1.git
                cd WebSite1
                unzip boocic.zip
                cd boocic
                cp -R * /var/www/html/
                
                '''
            }
            post{
                always{
                    echo "Install Httpd-It is always" 
                }
                success{
                    echo "Install Httpd-It is success"
                }
                failure{
                    echo "Install Httpd-It is failure"
                }
            }
        }
    }
    post{
        always{
            echo "Outsite-It is always" 
        }
        success{
            echo "Outsite-Install Httpd-It is always"
        }
        failure{
            echo "Outsite-Install Httpd-It is failure"
        }
    }
}
