node {
    stage('Preparation') { 
        git branch: 'master', url: 'https://github.com/shubhangist/jenkinsfilesrepo.git'
    }
    stage('Build') {
                sh 'mvn clean package'
            }
    stage('ArchiveResults') {
        archiveArtifacts 'target/*.war'
    }
}
