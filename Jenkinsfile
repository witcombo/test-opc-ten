node('vipkid-sgplm') {
    script{
        Service = env.Service
	Version = env.Version
    }
    stage('Clone') {
      git url: "https://github.com/witcombo/test-opc-ten.git"
    }
    stage('Test') {
      echo "2.Test Stage"
    }
    stage('Build') {
      echo "3.Build Docker Image Stage"
    }
    stage('Push') {
      echo "4.Push Docker Image Stage"
    }
    stage('YAML') {
      echo "5. Change YAML File Stage"
    }
    stage('Deploy') {
      echo "6. Deploy Stage"
    }
}
