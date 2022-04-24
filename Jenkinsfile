pipeline {
agent any
    environment {
                def nombreAplicacion= "httpd-jcamacho"
                def jobproject = "jcamacho-lab-dev"
    }

    stages{
        stage('Acceso a GitHub') {
        steps {
                checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'SparseCheckoutPaths']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://github.com/fsnsys/galhelloworld.git']]]
            }
        }

        stage('Build & Deploy') {
            steps {
                script {
                  openshift.withCluster() {
                    openshift.withProject("${jobproject}") {
                      openshift.startBuild("${nombreAplicacion}").logs('-f')
                    }
                  }
                }
            }
        }
    }
}
