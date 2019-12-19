// 30 Creating & configuring the Jenkinsfile

pipeline {      // declarative pipeline
    agent { label 'linux'}       // for this build use the node set up with label 'linux' (cf 12 Adding a build node)
    tools
    {
        maven 'M3'                  // build tool to use - need to ensure Maven is installed on whichever agent is used
    }
    stages
    {
        stage('checkout from SCM repo')
        {
            steps
            {
                //echo 'Hello there world!'
                git 'https://github.com/pjenkin/JenkinsProject30'
            }
        }
        stage ('Build')         // build the code
        {
            steps
            {
                sh 'mvn clear compile'
            }
        }
        stage ('Test')          // run tests
        {
            steps
            {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
                // Need to specify location of test results - junit for reporting in Jenkins
            }
        }
        stage ('Package')
        {
            sh 'mvn package'
        }
    }
// NB in my Vagrantfile/jenkins.sh I seem to have included JDK and JRE
}
// the actual source code (Java/Maven) from https://github.com/pjenkin/JenkinsProject30