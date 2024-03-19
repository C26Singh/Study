# Study
- How To Work With Multiple Github Accounts on a single Machine
- https://gist.github.com/rahularity/86da20fe3858e6b311de068201d279e3#file-work-with-multiple-github-accounts-md

## Command to test ssh  
- ssh -v git@github.com-Cksgitme

- Testing SSH Connection:  
  ssh -T git@github.com

- Debugging Git:  
  export GIT_SSH_COMMAND="ssh -v"

## How to generate ssh key
 - Generate SSH key pair for first GitHub account  
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f "filename"
