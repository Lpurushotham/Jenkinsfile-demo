pipeline{
    agent any
    tools{
        maven 'mymaven'
    }
    triggers{
        cron('* * * * *')
    }
    stages{
        stage('check out the code')
        {
            steps{
                git  'https://github.com/Lpurushotham/DevOpsCodeDemo.git'
            }
        }
        stage('compile the code')
        {
            steps{
                echo "compile the code...."
                sh 'mvn compile'
            }
        }
        stage('test the code')
        {
            steps{
                echo "test the code by using junit..."
                sh 'mvn test'
            }
        }
        stage('build the code')
        {
            steps{
                echo "generate the artifacts..."
                sh 'mvn package'
            }
        }
    }
}
