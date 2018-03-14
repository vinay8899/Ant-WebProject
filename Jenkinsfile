#! groovy
node{
 stage('Source'){
     git 'https://github.com/devopstrainingblr/Ant-WebProject.git'
     def branch = env.BRANCH_NAME
     if ($BRANCH_NAME == 'master') {
      println 'This happens only on master'
    } else {
      println "Current branch ${env.BRANCH_NAME}"
    }
 }
 
 stage('Build'){
    /* bat "ant -f build-mt.xml" */ /*For windows machines*/
    sh "ant -f build-mt.xml" 
 }
 stage('Send Email'){
     mail bcc: 'mithunreddytechnologies@gmail.com', body: 'Buils is done', cc: '', from: '', replyTo: '', subject: 'Build Status', to: 'devopstrainingblr@gmail.com'
 }
 /*stage('Archive'){
  archiveArtifacts '/Users/bhaskarreddyl/.jenkins/workspace/Pipeline-Project-Ant-Web/dist/SampleAntProject.war'
 }*/
}
