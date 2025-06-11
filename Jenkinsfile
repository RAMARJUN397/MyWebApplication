pipeline {
    agent any
    parameters {
        string(name: 'RUN_STAGE', defaultValue: 'stage1', description: 'Specify the stage to run')
    }
    stages {
        stage('stage1') {
            when {
                expression { params.RUN_STAGE == 'stage1' }
            }
            steps {
                echo 'Running Stage 1'
            }
        }
        stage('stage2') {
            when {
                expression { params.RUN_STAGE == 'stage2' }
            }
            steps {
                echo 'Running Stage 2'
            }
        }
    }
}
