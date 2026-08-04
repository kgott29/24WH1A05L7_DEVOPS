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
                    // FIX: Must use a plain, static string literal here to avoid syntax errors
                    stage('Run Test') {
                        steps {
                            echo "Testing on ${env.PLATFORM} using ${env.BROWSER}..."
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
