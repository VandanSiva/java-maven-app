pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("building jar"){
            steps{
                script{
                    echo "building the application"
                    sh 'mvn package'
                }
            }
        }
        stage("building image"){
            steps{
                script{
                    echo "building image"
                    withCredentials([usernamePassword(credentialsId: 'docker-cred', passwordVariable: 'PASS', usernameVariable: 'USER')]){
                        sh 'docker build -t 150419/demo-app:jma-2.0.1 .'
                        sh "echo $PASS | docker login -u $USER --password=stdin"
                        sh 'docker push 150419/demo-app:jma-2.0.1'
                    }
                }
            }
        }
        stage("deploy"){
            steps {
                script {
                    echo "deploying app"
                }
            }
        }
    }
}