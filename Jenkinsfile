pipeline {
  agent any
  tools {maven "mavenV3"}
  stages{
    stage("checkout"){
      steps{
        git branch: "main",
        url: "https://github.com/rikachinen24/SpringPetClinic.git"
      }
    }

    stage("build"){
      steps{
        sh "mvn compile"
      }
    }

    stage("test"){
      steps{
        sh "mvn test"
      }
    }

    stage("package"){
      steps{
        sh "mvn package"
      }
    }

    stage("deploy"){
      steps{
        sh "nohup java -jar \$(ls target/*.jar | head -1) &"
      }
    }
  }
}
