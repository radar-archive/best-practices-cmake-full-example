pipeline {
    agent {
        docker {
            registryUrl 'https://docker.inradar.net'
            registryCredentialsId 'radar-docker-registry'
            image 'docker.inradar.net/ubuntu-18.04-boost:0.1.3'
            args '-v /usr/local/share/ca-certificates/inradar-ca.crt:/usr/local/share/ca-certificates/inradar-ca.crt -v /etc/ssl/certs:/etc/ssl/certs -v /etc/ca-certificates.conf:/etc/ca-certificates.conf'
        }
    }

    stages {
        stage('Build') {
            steps {
                sh 'mkdir -p build && cd build && cmake .. && cd .. && cmake --build build -- -k -j 8'
            }
        }
    }
}
