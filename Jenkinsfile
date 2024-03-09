pipeline {
  // This line specifies that any agent can be used to run the pipeline. 
  agent any
  stages{

  // This defines a stage called "Build".
    stage('Build') {
    // This block defines the steps to be executed within the "Build" stage.
      steps {
      // This line prints a message to the console indicating that the build stage has begun.
        echo "This is Build stage."
        build 'non-existent-job'

      // This line compiles a C++ source file named "hello.cpp" located in the "main" directory, placing the output executable in a file named "output".
        sh 'g++ ./main/hello.cpp -o output'

      // This line prints a message to the console indicating that the build stage was successful.
        echo "Build Stage Successful"
      }
    }

  // This defines a stage called "Test".
    stage('Test') {
    // This block defines the steps to be executed within the "Test" stage.
      steps {
      // This line prints a message to the console indicating that the test stage has begun.
        echo "This is Test stage."

      // This line executes the "./output" command, which is likely the compiled program from the build stage. This is typically used to run unit tests for the application.
        sh './output'

      // This line prints a message to the console indicating that the test stage was successful.
        echo "Test Stage Successful"
      }
    }

  // This defines a stage called "Deploy".
    stage('Deploy') {
    // This block defines the steps to be executed within the "Deploy" stage.
      steps {
      // This line prints a message to the console indicating that the deployment stage has begun.
        echo "This is Deploy stage."

      // This line prints a message to the console indicating that the deployment was successful.  There is no actual deployment functionality included here. 
        echo "Deployment Success"
      }
    }
  }

  // This post block defines actions to be performed after the pipeline execution completes.
    post {
    // This block defines actions to be performed if the pipeline fails.
      failure {
      // This line sets an error message to be displayed if the pipeline fails.
        error 'Pipeline Failed'
      }
    }
  }
