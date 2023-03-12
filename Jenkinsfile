pipeline{
    agent{
        label{
            label "java-slave"
        }
    }
    tools{
        maven "M2_HOME"
    }
    stages{
        stage('Git'){
            steps{
                checkout changelog: false, poll: false, scm: scmGit(branches: [[name: 'master']], extensions: [], userRemoteConfigs: [[credentialsId: '44a98b45-ef5a-4718-bc00-c52d02397135', url: 'https://github.com/S-Raghu/jenkins-example.git']])
            }
        }
        stage('Build'){
            steps{
                sh 'mvn clean install package'
            }
        }
    }
}
