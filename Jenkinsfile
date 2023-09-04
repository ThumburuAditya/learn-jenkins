pipeline{
agent {
node{
label  'workstation'
}
}
stages{
stage('one'){
steps{
sh 'echo Helloworld'
}
}
}
post{
always{
sh 'echo Cleanup required'
}
}
}