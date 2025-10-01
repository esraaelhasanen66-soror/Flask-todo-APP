pipeline{

    agent any
    stages{

        stage('checkout'){

            steps{

                sh "ls -al"
                sh "ls -ltr"
                sh "pwd"
                sh "whoami"
            }


        }//checkout

        stage('Install requirements'){

            steps{

                sh "pip3 install -r requirements.text"
            }
        }

        stage('Test'){

            steps{

                sh "pytest"
            }
        }


    }
}