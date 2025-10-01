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

        // stage('Install requirements'){

        //     steps{

        //         //sh "python3 -m venv venv"
        //        // sh "source venv/bin/activate"
        //         //sh "pip install -r requirements.txt"
        //     }
        // }

        stage('Test'){

            steps{

                sh "pytest"
            }
        }


    }
}