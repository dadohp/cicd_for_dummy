pipeline {
         agent any
         stages {
                 stage('Build') {
                 steps {
                     echo 'Hi, Team_Dado. Starting to build the App.'
                 }
                 }
                 stage('Test') {
                 steps {
                    input('Do you want to proceed?')
                 }
                 }
                 stage('Deploy') {
                 parallel {
                        stage('Deploy start ') {
                           steps {
                                echo "Start the deploy .."
                           }
                           }
                        stage('Deploying now') {
                            agent {
                                    docker {
                                            reuseNode true
                                            image ‘nginx’
                                           }
                                    }

                              steps {
                                echo "Docker Created"
                              }
                           }
                           }
                           }
                 stage('Prod') {
                     steps {
                                echo "App is Prod Ready"
                              }

              }
}
}