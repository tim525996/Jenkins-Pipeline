pipeline {
    agent any
    environment {
        DIRECTORY_PATH = "Drectory path"
        TESTING_ENVIRONMENT = "Testing environment"
        PRODUCTION_ENVIRONMENT = "Tithira"
    }
    stages{
        stage('Build'){
            steps{
                echo "Build started and completed!"
                echo "fetch the  source  code  from  the  directory  path  specified  by  the  environment variable!"
                echo "compile the code and generate any necessary artifacts!"
        }
    }
        stage('Test'){
            steps{
                echo "Test started and completed!"
                echo "unit test"
                echo "integration test"
        }
    }
        stage('Code Quality Check'){
            steps{
                echo "Code Quality Check started and completed!"
                echo "check  the quality of the code"
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy started and completed!"
                echo "deploy  the  application  to  a  testing  environment specified by the environment variable"
            }
        }
        stage('Approval'){
            steps{
                echo "Approval started and completed!"
                timeout(time: 10, unit: 'SECONDS')
            {
                sleep(5)
            }
            }            
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploy to Production started and completed!"
                echo "Deploy the code $PRODUCTION_ENVIRONMENT!"
            }
        }
    }
}

