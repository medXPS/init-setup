node {

   

    stage('Checkout'){
        git branch: 'main',
            credentialsId: 'git',
            url: 'https://github.com/medXPS/init-setup.git'
    }



    stage('Deploy') {
     
        step([$class: 'KubernetesEngineBuilder',
            projectId: env.PROJECT_ID,
            clusterName: env.CLUSTER,
            location: env.ZONE,
            manifestPattern: 'K8s/',
            credentialsId:env.PROJECT_ID,
            verifyDeployments: true

        ])
    }
}
