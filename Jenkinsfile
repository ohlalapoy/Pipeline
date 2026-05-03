pipeline {
    agent any

    stages {
        stage('Check out Git') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], userRemoteConfigs: [[url: 'https://github.com/ohlalapoy/grpc.git']])
                sh 'mkdir -p python'
                dir('python'){
                    checkout scmGit(branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/ohlalapoy/Pythonlog.git']])
                }
                sh 'pwd'
                sh 'cp ./python/logging.py .'
            }
        }

        stage('Execute Doxygen File'){
            steps{ 
            //timestamp (format: YYYYMMDD-HHMMSS)
            script { env.TIMESTAMP = new Date().format("yyyyMMdd-HHmmss")}
            
            sh ''' 
            cp $HOME/Templates/Doxyfile_TaskC .
            doxygen Doxyfile_TaskC
            
            ''' 
                
            }
        }
        
        stage('Archive Docs') {
            steps {
                sh '''
                tar -czf doc-${TIMESTAMP}.tar.gz -C docs .
                cp doc-${TIMESTAMP}.tar.gz $HOME/TarFile/
                mkdir -p $HOME/Logs/${JOB_NAME}/${BUILD_ID}/
                mv $WORKSPACE/warning_log.log $HOME/Logs/${JOB_NAME}/${BUILD_ID}/
                '''
                archiveArtifacts artifacts: "doc-${TIMESTAMP}.tar.gz"
            }
        }
        stage('Generate Logs') {
            steps {
                sh '''
                python3 $WORKSPACE/logging.py -i $HOME/Logs/${JOB_NAME}/${BUILD_ID}/warning_log.log \
                -o $HOME/Logs/${JOB_NAME}/${BUILD_ID}/Results.csv
                cp $HOME/Logs/${JOB_NAME}/${BUILD_ID}/warning_log.log .
                cp $HOME/Logs/${JOB_NAME}/${BUILD_ID}/Results.csv .
                '''
                archiveArtifacts artifacts: "warning_log.log"
                archiveArtifacts artifacts: "Results.csv"
            }
        }
    }
}