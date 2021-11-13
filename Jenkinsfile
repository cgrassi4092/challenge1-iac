pipeline {
    agent any
    environment {
        Divisor = '==================== ########### ===================='
        Distro = '==================== Distro Info ===================='
        Kernel = '==================== Kernel Info ===================='
        Users = '==================== Users Info  ===================='
        Packages = '=================== Packages Info ==================='
    }
    stages {
        stage('Distro Info') {
            steps {
                sh '> assessment.txt'
                sh 'echo $Divisor >> assessment.txt'
                sh 'echo $Distro >> assessment.txt'
                sh 'echo $Divisor >> assessment.txt'
                sh 'echo   >> assessment.txt'
                sh 'cat /etc/*-release >> assessment.txt'
            }
        }        
        stage('Kernel Info') {
            steps {
                sh 'echo   >> assessment.txt'
                sh 'echo $Divisor >> assessment.txt'
                sh 'echo $Kernel >> assessment.txt'
                sh 'echo $Divisor >> assessment.txt'
                sh 'echo   >> assessment.txt'
                sh 'uname -a >> assessment.txt'
            }
        }
        stage('Users Info') {
            steps {
                sh 'echo $Divisor >> assessment.txt'
                sh 'echo $Users >> assessment.txt'
                sh 'echo $Divisor >> assessment.txt'
                sh 'cat /etc/passwd | cut -d: -f1 >> assessment.txt'
            }
        }
        stage('Packages Info') {
            steps {
                sh 'echo   >> assessment.txt'
                sh 'echo $Divisor >> assessment.txt'
                sh 'echo $Packages >> assessment.txt'
                sh 'echo $Divisor >> assessment.txt'
                sh 'echo   >> assessment.txt'
                sh 'dpkg -l >> assessment.txt'
            }
        }
        stage('Deploy Info') {
            steps {
                echo 'Gerando o arquivo e disponibilizando no Repositório'
               
            }
        }
    }
    post {
            always {
                echo 'Resultado da execução do Pipeline: '
            }
            success {
                echo 'Compilação Finalizada com sucesso!'
            }
            failure {
                echo 'Erro no processamento.'
            }
        }
}
