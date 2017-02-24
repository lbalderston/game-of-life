node {
   stage 'Stage 1'
   echo 'Hello World 1 this is my other branch'
   stage 'Stage 2'
   echo 'Hello World 2'
   stage 'Stage 3'
   git 'https://github.com/jenkinsci/docker'
   sh """
   	ls -l 
   	cat README.md
   """
   /* echo "foo is $foo"
   if (foo == 'true') {
   	sh 'ls -l'
   
   } else {
   	echo "foo is false"
   	sh 'cat docker-compose.yml'
   }*/
   
}
/*stage 'user input'
def userInput = input(
	id: 'userInput', message: 'Is it ok to push to server?', parameters: [
	[$class: 'TextParameterDefinition', defaultValue: 'ok', description: 'Push to prod', name: 'prodcheck']
	])
	echo ("User input: " +userInput)
*/	
stage 'loop'
for (def i=0; i < 20; i++) {
	echo "building $i"
	sleep 1

}

parallel firstBranch: {
	for (def i=1; i<20; i++){
		echo "building ... $i"
		sleep 1
	}
}, secondBranch: {
	for (def i=1; i<10; i++){
		echo "building in parallel ... $i"
		sleep 2
	}
}
