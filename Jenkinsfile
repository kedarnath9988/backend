pipeline{
        agent {
            label 'node-01'
        }
        options {
            timeout(time:30, unit:'MINUTES')
            disableConcurrentBuilds()
            ansiColor('xterm')
        }

        environment{
        def application_version = ' '
        }
        stages {

            stage('get_version'){
                steps{
                    script{
                        def app_version = readJSON file: 'package.json'
                        application_version = app_version.version 
                        echo " current version is : $application_version"

                    }
                    /* script {
                     def app_version  = readJSON file: 'package.json'
                    application_version = app_version.version 
                    echo "application version is: $application_version"
                    } */
                } 
            }
                
                stage('install dependencies'){
                    steps {
                        sh """
                        npm install 
                        ls -ltr 
                        echo " current version is : $application_version"
                        """
                    }
                }
                stage('create zip-file'){
                    steps{
                        sh """
                            zip backend-${application_version} * -x Jenkinsfile -x  backend-${application_version}
                       """
                    }       
            }
                
                
        }
        post {
            always {
                echo 'i will run laways '
                deleteDir()
            }
            success {
                echo 'pipeline is successfull'
            }
            
        }
}
