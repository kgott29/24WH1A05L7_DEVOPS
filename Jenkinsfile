pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        
        stage('Test') {
            matrix {
                // 1. Define your matrix combinations
                axes {
                    axis {
                        name 'PLATFORM'
                        values 'linux', 'windows', 'mac'
                    }
                    axis {
                        name 'BROWSER'
                        values 'chrome', 'firefox'
                    }
                }
                
                // 2. Define stages to execute for every combination
                stages {
                    stage('Executing Matrix Test') {
                        steps {
                            echo "Testing on ${PLATFORM} using ${BROWSER}..."
                        }
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }    
    }
}
