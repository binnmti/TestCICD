node {
	stage 'Checkout'
		checkout scm

	stage 'Build'
		bat 'nuget restore TestCICD.sln'
		bat "\"${tool 'MSBuild14'}\"msbuild TestCICD.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"

	stage 'Archive'
		archive 'bin/Release/**'

}