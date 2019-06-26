node('vipkid-sgplm') {
    script{
        Service = env.Service
	Version = env.Version
    }
    stage('Clone') {
      	sh "git clone https://github.com/witcombo/test-opc-ten.git -b ${Service} && cd /test-opc-ten/${Service}"
    }
    stage('wget') {
      	echo "2.Test Stage"
      	sh "echo '172.31.0.39 harbor.vipkid-qa.com.cn' >> /etc/hosts;wget -c -r -nd -np -k -L -p --user=vipkid --password='rJAznMiYSpWaUuWI' http://10.104.36.9:18888/sgplm/$Service/$Version/"
    }
    stage('Build') {
      	sh "docker build -t harbor.vipkid-qa.com.cn/sgplm-test/sgplm-${Service}:${Version} ."
    }
    stage('Push') {
      	sh "docker push harbor.vipkid-qa.com.cn/sgplm-test/sgplm-${Service}:${Version}"
    }
    stage('YAML') {
      	echo "5. Change YAML File Stage"
    }
    stage('Deploy') {
      	echo "6. Deploy Stage"
    }
}
