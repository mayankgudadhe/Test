pipeline {
    agent {
        label {
            label "slave"
            customWorkspace "/mnt/test"
        }
    }
    parameters{
        choice(name : "branch",choices:["master","2024-Q1"],description : "Select branch")
    }
    stages {
        stage("Install"){
            steps {
                sh "sudo yum install git -y"
                sh "sudo yum install maven -y"
            }
        }
        stage("Clone"){
            steps {
                git branch :"${params.branch}" , url :"https://github.com/Shantanumajan6/project.git"
            }
        }
    }
}
