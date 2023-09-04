pipeline{
triggers{
pollSCM('H/2 * * * *')
}
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
 input {
                message "Do you want to continue?"
                ok "Yes"
}
steps{
sh 'echo Helloworld'
sh 'echo ${sample_url}'
sh 'echo PERSON - ${name}'
}
}
stage('Two'){
when {
expression {
GIT_BRANCH == "origin/test"
}
}
steps{
sh 'env'
}
}
}
post{
always{
echo 'Cleanup required'
}
}
}
}
