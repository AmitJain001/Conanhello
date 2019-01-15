node{
	def server = Artifactory.server "artifactory"
	def client = Artifactory.newConanClient userHome: "/home/ajain"
	def name = client.remote.add server: server,repo = "conan-local"

	stage ("Get recipe"){
		checkout scm	
	}
	stage("Create package"){
		client.run(command: "create . amit/user -s build_type=Debug")
	}
	stage("Upload packages"){
		string command = "upload Hello* --all -r ($name) ---cofirm"
		def b = client.run(command:command)
	}
}
