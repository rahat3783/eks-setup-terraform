pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION = 'us-east-1'
    }
    stages{
        stage("Clone Code"){
            steps{
                git url: "https://github.com/rahat3783/eks-setup-terraform.git", branch: "main"
                echo "successfully clonning"
            }
        }
      stage(Initializing Terraform){
        steps{
          sh 'terraform init'
        }
      }
      stage(Validate terraform){
        steps{
          sh 'terraform validate'
        }
      }
       stage(Previewing Infrasructure){
        steps{
          sh 'terraform plan'
        }
      }
       stage(creating eks cluster){
        steps{
          sh 'terraform apply --auto-approve'
        }
      }
    }
