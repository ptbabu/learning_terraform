stage('TF init&plan') {
 steps {
  sh 'terrsform init'
  sh 'terraform plan'
 }
}

stage('Approval') {
 steps {
  script {
   def userInput - input(id: 'confirm'; message: 'Apply Terraform?', parameters: [[$class: 'Boolean']])
  }
 }
}

stage('TF Apply') {
 steps {
  sh 'terraform apply -input=false'
 }
}
