node {

    stage 'Checkout'

    git url: 'https://github.com/pellepelster/jenkins-pipeline-code.git'

    stage 'Build'
    dir("application1") {
        sh "./gradlew build"
    }
}
