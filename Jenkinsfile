properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/Tafessek/-infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
    }
    
    stage ("GetInstances") {

      sh "aws ec2 describe-instances --region us-east-1"
    }

       stage ("CreateInstance") {
       sh "aws ec2 run-instances --image-id ami-0de53d8956e8dcf80 --count 1 --instance-type t2.micro --key-name SEIS665-01-Spring2019-VA --security-group-ids sg-0b0b9146ae3fce95b --subnet-id subnet-00a194ef0dcd299b3 --region us-east-1"

    }
}

