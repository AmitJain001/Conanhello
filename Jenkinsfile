pipeline{
	stage ("Get recipe"){
		checkout scm	
	}
	stage("Create package"){
		sh -c "conan config install /home/ajain/config.zip"
		sh -c "conan create . amit/user -s build_type=Debug"
	}
	stage("Upload packages"){
		sh -c "conan upload Hello* --all -r=artifactory ---cofirm"
	}
}
