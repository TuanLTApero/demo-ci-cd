pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Lấy code về khi có pull request vào branch master
                checkout scm
            }
        }

        stage('Echo pod Path') {
            steps {
                script {
                    def podPath = sh(script: 'which pod', returnStdout: true).trim()
                    echo "Path to 'pod' executable: ${podPath}"
                }
            }
        }
        
    //     stage('Build Dev Schema') {
    //         steps {
    //             // Sử dụng xcodebuild để build schema 'dev'
    //             sh 'xcodebuild -workspace demo-ci-cd.xcworkspace -scheme demo-ci-cd-dev -destination "platform=iOS Simulator,name=iPhone 11" build'
    //         }
    //     }
    //     stage('Build Product Schema') {
    //         steps {
    //             // Sử dụng xcodebuild để build schema 'product'
    //             sh 'xcodebuild -workspace demo-ci-cd.xcworkspace -scheme demo-ci-cd -destination "platform=iOS Simulator,name=iPhone 11" build'
    //         }
    //     }
    //     stage('Deploy') {
    //         when {
    //             // Chỉ triển khai nếu bước build thành công
    //             expression { currentBuild.resultIsBetterOrEqualTo('SUCCESS') }
    //         }
    //         steps {
    //             script {
    //                 // Triển khai schema 'dev' lên DeployGate
    //                 sh 'fastlane deploy_to_deploygate'

    //                 // Triển khai schema 'product' lên TestFlight
    //                 sh 'fastlane deploy_to_testflight'
    //             }
    //         }
    //     }
    // }
    // post {
    //     failure {
    //         // Nếu bất kỳ bước nào trong pipeline fail, bạn có thể thực hiện các hành động ở đây
    //         echo "Build failed! Deployment skipped."
    //     }
    //     success {
    //         // Nếu tất cả các bước trong pipeline thành công, bạn có thể thực hiện các hành động ở đây
    //         echo "Build and deploy succeeded!"
    //     }
    // }
}