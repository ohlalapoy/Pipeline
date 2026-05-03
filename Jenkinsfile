pipeline {
    agent any

    stages {
        stage('Check out Git') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/ohlalapoy/grpc.git']])
                sh ''' pwd'''
            }
        }

        stage('Execute Doxygen File'){
            steps{ 
            //timestamp (format: YYYYMMDD-HHMMSS)
            script { env.TIMESTAMP = new Date().format("yyyyMMdd-HHmmss")}
            
            sh ''' 
            cp $HOME/Templates/Doxyfile .
            doxygen Doxyfile
            
            ''' 
                
            }
        }
        
        stage('Archive Docs') {
            steps {
                sh '''
                tar -czf doc-${TIMESTAMP}.tar.gz -C docs .
                cp doc-${TIMESTAMP}.tar.gz $HOME/TarFile/
                '''
                archiveArtifacts artifacts: "doc-${TIMESTAMP}.tar.gz"
            }
        }
    }
}