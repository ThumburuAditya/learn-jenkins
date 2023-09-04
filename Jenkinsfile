pipeline{
triggers{ cron('H/2 * * * *') }
options {
        ansiColor('xterm')
    }
agent {
node{
label  'workstation'
}
}
environment {
sample_url = "example.com"
}
parameters{
 string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
 }
stages{
stage('one'){
steps{
sh 'echo Helloworld'
sh 'echo ${sample_url}'
sh 'echo PERSON - ${name}'
}
}
}
post{
always{
sh 'echo Cleanup required'
}
}
}