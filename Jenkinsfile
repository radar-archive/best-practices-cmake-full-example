// Copyright 2019 RADAR, Inc. - All Rights Reserved
// Proprietary and confidential

pipeline {
    agent {
        docker {
            registryUrl 'https://docker.inradar.net'
            registryCredentialsId 'radar-docker-registry'
            image 'docker.inradar.net/ubuntu-20.04-boost:0.2.0'
        }
    }

    environment {
        PREFIX = "${WORKSPACE}/installed"
    }

    stages {
        stage('Build') {
            steps {
                sh 'mkdir -p build && cd build && cmake -DCMAKE_INSTALL_PREFIX=${PREFIX} .. && cd .. && cmake --build build -- -k -j 8'
            }
        }
        stage('Test') {
            steps {
                sh 'ctest --no-compress-output -T Test || true'
                xunit(tools: [CTest(pattern: 'Testing/*/Test.xml')])
            }
        }
        stage('Install') {
            steps {
                sh 'cmake --build build --target install'
            }
        }
    }
}
