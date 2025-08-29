pipeline {
    agent any

    stages {
        stage('Build') {
            stages {
                stage('Compile') {
                    steps {
                        echo 'Compiling...'
                        sleep 2
                    }
                }
                stage('Package') {
                    steps {
                        echo 'Packaging...'
                        sleep 3
                    }
                }
            }
        }

        stage('Registering build artifact') {
            steps {
                echo 'Registering the metadata'
                echo 'Another echo to make the pipeline a bit more complex'
                registerBuildArtifactMetadata(
                    name: "Demo-jenkins-runs-BT-feature-2",
                    version: "1.0.1",
                    type: "docker",
                    url: "http://localhost:4001",
                    digest: "6f637064707039346163663237383761",
                    label: "Internal-demo-BT-artifact-Prod"
                )
            }
        }

        stage('Test') {
            steps {
                echo 'Running Unit Tests...'
                sleep 7
                echo 'Running Integration Tests...'
                sleep 5
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sleep 4
            }
        }
    }
}
