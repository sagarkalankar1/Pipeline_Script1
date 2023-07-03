pipeline{
    agent any
    stages {
        stage('Git-Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/sagarkalankar1/Pipeline_Script1.git'
            }
        }
        
        stage('Build') {
            steps {
                echo "Building the checked-out project";
                sh 'chmod +x Build.sh'
                sh './Build.sh'
            }
        }
        stage('Unit-Test') {
            steps {
                echo "Running the Unit Test";
                sh 'chmod +x UnitTest.sh'
                sh './UnitTest.sh'
                /*sh exit ("1");*/
            }
        }
        stage('Quality-Gate') {
            steps {
                echo "Verifying Quality Gates";
                sh 'chmod +x Quality.sh'
                sh './Quality.sh'
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying to Stage Environment for more tests";
                sh 'chmod +x Deploy.sh'
                sh './Deploy.sh'
            }
        }

        stage('Java') {
            steps {
               sh 'javac Hello.java'
               sh 'java Hello'
            }
        }

    }
}
