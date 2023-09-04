pipeline{
agent {
node{
label  'workstation'
}
}
environment {
sample_url = "example.com"
}
stages{
stage('one'){
steps{
sh 'echo Helloworld'
sh 'echo ${sample_url}'
}
}
}
post{
always{
sh 'echo Cleanup required'
}
}
}