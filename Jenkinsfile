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
                    //gv.buildImage()
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
