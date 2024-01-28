pipeline{  
agent any 
stages{ 
stage('Build Application') { 
steps { 
bat 'mvn clean install' 
} 
} 
stage('Deploy CloudHubs') { 
environment { 
ANYPOINT_CREDENTIALS = credentials('al0159330') 
} 
steps { 
echo 'Deploying mule project due to the latest code commit…' 
echo 'Deploying to the configured environment….' 
bat 'mvn clean deploy -DmuleDeploy -Dusername=al0159330 -Dpassword=Akshay@123 -DworkerType=Micro -Dworkers=1 -DobjectStoreV2=true' 
}  
} 
} 
} 
