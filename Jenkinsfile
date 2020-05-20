// Шаблон пайплайна. 
// Наши требования к разработке пайплайна https://stackoverflow.com/c/bit-erp/questions/298/299#299
// Общий кодстайл https://google.github.io/styleguide/javaguide.html


pipeline {

    agent {
        label "master"
    }

    options {
        timeout(time: 3600, unit: 'SECONDS') 
        buildDiscarder(logRotator(numToKeepStr: '10'))
        skipDefaultCheckout true
    }
    
    stages {
        stage('Перед запуском сборки') {
            steps {
                timestamps {
                    script {
                        echo "start"
                    }
                }
            }
        }
        stage("Выполнение") {
            steps {
                timestamps {
                    script {
                       param1 = "param1_test"
                    }
                }
            }
        }
    }

    post {
        always {
            script {
                echo param1
            }
        }
    }
}