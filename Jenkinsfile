pipeline {
    agent {
        label 'lin'
    }
    stages {
//         stage('Git') {
//             steps{
//                 git branch: 'master', url: 'https://github.com/Apoddubniy/vector-role.git'
//             }
//         }
        stage ('Molecule version'){
            steps {
                sh 'molecule --version'
            }
        }
        stage('Molecule test'){
            steps{
                sh 'molecule test -s docker'
                cleanWs()
            }
        }
    }
}