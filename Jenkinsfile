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
                echo "Build started with Maven and completed!"
                echo "fetch the  source  code  from $DIRECTORY_PATH!"
                echo "compile the code and generate any necessary artifacts!"
        }
    }
        stage('Unit and Integration Tests'){
            steps{
                echo "Unit and Integration testing...."
                echo "Unit and Integration Tests started and completed with JUnit!"
                echo "unit test"
                echo "integration test"
                writeFile file: 'build.log', text: 'Build log content for demonstration.'
            }
            post {
                mail to: "tithira.m@gmail.com"
                success {                    
                    script {
                        // Send email on success with log file attached
                        emailext(
                            to: "tithira.m@gmail.com",
                            subject: "Unit and Integration Tests Status Email",
                            body: "Unit and Integration Tests were successful! Please find the test log attached.",
                            attachmentsPattern: 'test-results.log'
                        )
                    }
                }
                failure {
                    script {
                        // Send email on failure with log file attached
                        emailext(
                            to: "tithira.m@gmail.com",
                            subject: "Unit and Integration Tests Status Email - FAILURE",
                            body: "Unit and Integration Tests failed. Please see the attached log for details.",
                            attachmentsPattern: 'test-results.log'
                        )
                    }
                }
            }                                           
    }
        stage('Code Analysis'){
            steps{
                echo "Code Analysis started and completed with SonarQube!"
                echo "check  the quality of the code"
            }
        }
        stage('Security Scan'){
            steps{
                echo "Security scan running...."
                echo "Security Scan started and completed with OWASP ZAP!"
                echo "deploy  the  required security measurements against the vulnerabilities, specified by the security scan "                
            }
            post{
                success{                    
                    mail to: "tithira.m@gmail.com",
                    subject: "Security Scan Status Email",
                    body: "Security Scan was successful!"                                        
                }
            }                       
        }
           stage('Deploy to Staging'){
            steps{
                echo "Deploy to staging started and completed with AWS EC2!"
                echo "deploy  the  application  to  a  testing  environment specified"
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo "Integration Tests on Staging started and completed with Selenium!"
                timeout(time: 10, unit: 'SECONDS')
            {
                sleep(5)
            }
            }            
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploy to Production started and completed with AWS EC2!"
                echo "Deploy the code $PRODUCTION_ENVIRONMENT!"
            }
        }
    }
}

