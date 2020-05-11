pipeline {
    agent any
    stages {
        stage('Git clone') { 
            steps {
                git url: 'https://github.com/sefremidis/Quiz2_MathApp.git'
            }
        }
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Execute app') {
            steps {
                sh 'java -cp target/gr.CCP6418.Quiz2-0.0.1-SNAPSHOT.jar:dir/* MathApp'
            }
        }
    }
    post {
        success  {
            echo "Execute when run is successful."
        }
        failure  {
            echo "Execute run results in failure."
        }
    }
}