pipeline{
        agent {
            label 'node-01'
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
                       
                    npm install

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
