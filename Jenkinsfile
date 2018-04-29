node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("cicdpipeline/test1")
		sh 'echo "Build successful"'
    }

    stage('Run image') {
        /* Ideally, we would run a test framework against our image.
         * For this example, we're using a Volkswagen-type approach ;-) */

            sh 'docker run -d -p 8000:8000 "cicdpipeline/test1"'
			sh 'docker container ls -all'
			sh 'echo "Container app started"'
          }

  }
