node {
	
	stage('Clone')
	    checkout poll: false, scm: [$class: 'GitSCM', branches: [[name: 'apps']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'SparseCheckoutPaths', sparseCheckoutPaths: [[path: 'advanceSettings/']]]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'd4e8a91c-5692-4120-852d-110775ea41bb', url: 'git@github.com:JMCRACKER/jccsb.git']]]
	    jdk = tool name: 'jdk7'
        env.JAVA_HOME = "${jdk}"
        echo "jdk installation path is: ${jdk}"
        sh "${jdk}/bin/java -version"
        sh '$JAVA_HOME/bin/java -version'
	
	stage('Build')
	    {
                
        sh " mvn -f advanceSettings/trunk/ clean install -U -Dwagon.skip=true"
                
        }
	stage('SonarQube analysis') {
	    
	    sh 'mvn -f advanceSettings/trunk/  sonar:sonar  -Dsonar.host.url=http://172.31.10.222:9000   -Dsonar.login=32ec17a4925ca1aa2f32f7e1e3dc948e89aa601e'
    }
}