node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("kraniotisk/example-app")
    }

    stage('Push image') {
        /* Finally, we'll push the image into Docker Hub */

        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-kkran2') {
            app.push("latest")
        }
    }
}
