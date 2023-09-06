pipeline{
    agent any
    tools{
        maven "test-maven"
    }
    stages{
        stage("compile by qprofiles"){
            steps{
                sh 'mvn compile'
                recordIssues(tools: [pmdParser()])
            }
        }
        stage("testing by qprofiles"){
            steps{
                sh 'mvn test'
            }
        }
        stage("qa by qprofiles"){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage("package by qprofiles"){
            steps{
                sh 'mvn package'
            }
        }
    }
}
