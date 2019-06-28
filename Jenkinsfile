node('vipkid-sgplm') {
    script{
        Service = env.Service
        Version = env.Version
    }
    stage('Clone') {
        echo "1. Clone"
        sh "git clone https://github.com/witcombo/test-opc-ten.git -b ${Service} && cd test-opc-ten/${Service}"
    }
    stage('Curl') {
        echo "2. Curl"
        sh "echo '172.31.0.39 harbor.vipkid-qa.com.cn' >> /etc/hosts;curl -O http://10.104.36.9:18888/sgplm/${Service}/${Version}/${Service}"
    }
    stage('Build') {
        echo "3. Build"
        withCredentials([usernamePassword(credentialsId: 'harbor', passwordVariable: 'harborPassword', usernameVariable: 'harborUser')]) {
            sh "docker login harbor.vipkid-qa.com.cn -u ${harborUser} -p ${harborPassword}"
            sh "docker build -t harbor.vipkid-qa.com.cn/sgplm-test/sgplm-${Service}:${Version} test-opc-ten/${Service}/"
        }
    }
    stage('Push') {
        echo "4. Push"
        sh "docker push harbor.vipkid-qa.com.cn/sgplm-test/sgplm-${Service}:${Version}"
    }
    stage('YAML') {
        echo "5. Change YAML File Stage"
    }
    stage('Deploy') {
        echo "6. Deploy Stage"
    }
    stage('ShortText') {
        echo "7. add ShortText"
        manager.addShortText(manager.build.buildVariables.get("service"))
        manager.addShortText(manager.build.buildVariables.get("version"))
    }
}
