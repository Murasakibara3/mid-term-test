#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

void main() {
	pid_t pid;
	int status =0;

	// child process
	if((pid=fork()) ==0) {
		printf("Child PID is %d, Parent PID is %d.\n",getpid(),getppid());
		return 0;
	} 
	
	// parent process
	else {
		while(!waitpid(pid, &status, WNOHANG));
		printf("Parent PID is %d\n", getpid());
	}
	return 0;
}
