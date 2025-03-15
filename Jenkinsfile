pipeline{
        agent {
            label 'backend-01'
        }
        options {
            timeout(time:30, unit:'MINUTES')
            disableConcurrentBuilds()
            ansiColor('xterm')
        }
        stages {
                
                stage('install dependencies'){
                    steps {
                        sh """
                    sudo   dnf module disable nodejs -y
                    sudo   dnf module enable nodejs:20 -y
                    sudo   dnf install nodejs -y

                    ifconfig -a
                    
                        """
                    }
                }
                stage('create zip-file '){
                    steps{
                        sh """
                            echo create zip-file
                            
                       """
                    }       
            }
                
                
        }
        post {
            always {
                echo 'i will run laways '
               
            }
            success {
                echo 'pipeline is successfull'
            }
            
        }
}
