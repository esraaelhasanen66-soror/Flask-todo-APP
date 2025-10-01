pipeline{

    agent any
    environment{
        IMAGE_NAME='esraaelhasanen/jenkins-flask-app'
        IMAGE_TAG="${IMAGE_NAME}:${env.BUILD_NUMBER}"

    }
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

                 
                sh "python3 -m venv venv"
                sh "venv/bin/pip install --upgrade pip"
                sh "echo dd"
                sh "echo wel"
                sh "pwd"
                sh "whoami"
                sh "venv/bin/pip install -r requirements.txt"
                sh "pwd"
                sh "whoami"

                
            }
        }

        stage('Test'){

            steps{

                //sh "pytest"
                sh "venv/bin/python -m pytest"
            }
        }
        stage('Login to Dcoker hub'){

            steps {
                withCredentials([string(credentialsId: 'dockerhubpass', variable: 'dockerhubpass')]) {
                sh 'echo ${dockerhubpass} | docker login -u esraaelhasanen --password-stdin'}
                echo 'Login successfully'
            }
        }

        stage('Build Docker image'){

            steps{

                sh "docker build -t $IMAGE_TAG ."
                sh "docker image ls"
            }


        }
        stage('Push to DcokerHub'){

            steps{

                sh "docker push $IMAGE_TAG"
            }
        }

        stage('update image name on compose file'){

            steps{

                 sh "sed -i 's|image: img|image: $IMAGE_TAG|' docker-compose.yaml"
            }
        }

        stage('Run compose file'){

            steps{

                sh "docker compose up -d"
            }
        }


    }
}