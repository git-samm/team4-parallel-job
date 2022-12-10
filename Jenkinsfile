pipeline{
    agent any
    stages{
        stage('1-clone'){
            steps {
                sh 'cat /etc/passwd'
            }
        }
        stage('2-parallel-jobs'){
            parallel{
                stage('1-subjob1'){
                    steps {
                        sh 'lscpu'
                    }
                }
                stage('2-subjobs'){
                    when {
                        branch 'future'
                    }
                    steps {
                        sh 'df -h'
                    }
                }
                
            }
        }
        stage('3-codeTest'){
                    steps {
                        sh 'free -m'
                    }
                }
                stage('4-closing'){
                    when {
                        branch 'future'
                    }
                    steps {
                        echo "We are done"
                    }
                }
    }
    }