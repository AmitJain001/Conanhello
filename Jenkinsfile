pipeline{
	agent any
	environment {
    		PATH = "/home/ajain/Downloads/cmake-3.13.3/bin:$PATH"
	}
	stages{
		stage ("Get recipe"){
			steps{
				checkout scm	
			}
		}
		stage("Create package"){
			steps{
				sh "conan config install /home/ajain/config.zip"
				sh "conan create . amit/user -s build_type=Debug"
			}
		}
		stage("Upload packages"){
			steps{
				sh "conan upload Hello* --all -r=artifactory ---cofirm"
			}
		}
	}
}
