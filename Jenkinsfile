# Jenkinsfile
node{
    def project = 'env-test-218803'
    def appName = 'test'
    def tag = "v_${env.BUILD_NUMBER}"
    def img = "gcr.io/${project}/${appName}-${env.BRANCH_NAME}"
    def imgWithTag = "${img}:${tag}"
    
    checkout scm

    stage '建立映像檔'
    sh("docker build -t ${imgWithTag} .")

    stage '放置映像檔'
    sh("gcloud docker -- push ${imgWithTag} ")
}