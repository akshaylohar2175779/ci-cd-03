pipeline {
  agent any
  environment {
  //adding a comment for the commit test
  DEPLOY_CREDS = credentials('mulesoft-releases')
  MULE_VERSION = '4.4.0'
  BG = "dellc"
  WORKER = "Micro"
  M2SETTINGS = "C:\\Users\\aksha\\.m2\\settings.xml"
  }
  stages {
  stage('Build') {
  steps {
  bat 'mvn -B -U -e -V clean -gs %M2SETTINGS% -DskipTests package'
  }
  }
 
  
  stage('Deploy Sandbox') {
  environment {
  ENVIRONMENT = 'Sandbox'
  APP_NAME = 'ci-cd-03-pipe'
  }
  steps {
  bat 'mvn -U -V -e -B -gs %M2SETTINGS% -DskipTests deploy'
  }
  }
  }
  }
