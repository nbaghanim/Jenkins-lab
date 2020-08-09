pipeline {
        agent   {docker {image 'alpine:3.7'}}
        options { skipStagesAfterUnstable() }
        stages  {
                stage('BuildStaging') { steps { echo 'creating infra for staging' } }
                stage('DeployStaging'){ steps { echo 'deploying application on staging environment' } }
                 stage('ValidateStageDeployment') {steps { echo 'validate deployment on staging' } }
         }
 }
