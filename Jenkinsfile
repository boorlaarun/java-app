pipeline {
     agent any
    }
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    stages{
        stage("build code"){
            steps{
                sh 'mvn clean install'
            }
            
        }
    }
post {
         always {
             echo 'This will always run'
         }
         success {
             echo 'This will run only if successful'
			// archiveArtifacts artifacts: '**/*.war', fingerprint: true
         }
        //failure {
          //   mail bcc: '', body: "<b>Build Report</b><br>\n<br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL of build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Jenkins CI: Project name ${env.JOB_NAME}, Build No ${env.BUILD_NUMBER}", to: email_ids;
         //}
		
         unstable {
             echo 'This will run only if the run was marked as unstable'
         }
         changed {
             echo 'This will run only if the state of the Pipeline has changed'
             echo 'For example, if the Pipeline was previously failing but is now successful'
         }
     }

