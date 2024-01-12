pipeline {
    agent any

    environment {
        FLUTTER_CHANNEL = 'stable'
        FLUTTER_VERSION = '3.10.2'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    git 'https://github.com/Olfasalem/appflutter.git'
                }
            }
        }

        stage('Setup Flutter') {
            steps {
                script {
                    echo "Installing Flutter"
                    bat 'git clone -b %FLUTTER_CHANNEL% https://github.com/flutter/flutter.git'
                    bat 'set PATH=%PATH%;%cd%/flutter/bin'
                    bat 'flutter --version'
                }
            }
        }

        stage('Flutter Packages') {
            steps {
                script {
                    echo "Getting Flutter packages"
                    bat 'flutter pub get'
                }
            }
        }

        stage('Flutter Test') {
            steps {
                script {
                    echo "Running Flutter tests"
                    bat 'flutter test'
                }
            }
        }

        stage('Build APK') {
            steps {
                script {
                    echo "Building APK"
                    bat 'flutter build apk'
                }
            }
        }

        
        }
    

   
    

}
