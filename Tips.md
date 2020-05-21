# Tips and Tricks

## Tips

####  Keep track of your time
The exam will last for 2 hours, it gives you a 6 min per question, some questions represents only 2% or 3% of the total exam score. Avoid spending too much time on low scoring questions, if you get stuck in one of these, skip to the next one and leave these to be completed at the end.

> **Important notice**:  
> On *kubernetes 1.18*, the flag `--dry-run` and the command `run` has been deprecated.  
`--dry-run` is still valid on 1.18 but it will generate a warning, the correct way to use it is via `--dry-run=server` or `--dry-run=client`
`run` command will only generate pods. please check [kubectl tips](Kubectl.md) for more examples.


#### Take some exercises before the exam. 

I've notice experienced people fail the exam on first attempt, people who work with kubernetes on daily basis, mainly because the test covers quite a few different scenarios we don't usually interact with everyday.

People whith over 1 year of experience will likely pass the test withtout much difficulties, you should try some exercises to assert your skills on all areas required by the exam to not be caught by surprise.

If your experienced with kubernetes is short, reading the docs is the best starting point, but it is a tedious and long task and does not point you to right direction, the resources provided here try to give you some directions, you should also try the exercises multiple times and get prepared for the exam.

####  Do not create yaml files from scratch
To make best use of your time, you should avoid typing the yaml files by hand, it is a tyme consuming task and there are better way of doing it. 

The first is using the cli `kubectl` with the flags `--dry-run -o yaml` to generate the yaml file for you, the example below will output the yaml to the terminal: 
```
kubectl run nginx --image=nginx --dry-run=client -o yaml
```

---
## Tools

The following is a list of tools commonly used while working with kubernetes. Knowing the basics of these tools will save you some time during the exam.

---
### bash

Bash is the default shell in most linux distros, the VM running the test will have it, making good use of the shell is the first priority for anyone working with kubernetes.

**Alias**:
aliases are very useful to save time with commands that are done really often, in the exam, you will type the `kubectl` command many times, the command itself is not long, but savind some time is valuable given the short. The command can be aliased to:

`alias k=kubectl`

Every time you need to use `kubectl` you can just type `k`, e.g:

``` 
kubect get pods
k get pods
```

**Shortcuts**:

    CTRL + Z    -> Suspend current active program
    fg          -> Restore last suspended(or fg %2)
    jobs        -> list background jobs

    CTRL + R    -> bash history search
    

---
### kubectl

kubectl is the cli used to interact with Kubernetes api. This is the tool you must master to pass the test without pressure. 

Make sure you are using the cli based on same version of your exam. To get the cli version use the following command: `kubectl version`

In case you don't want to use the defaul editor while modifying resources e.g. `kubectl edit pod nginx`. You can change the default editor by changing the environment variable `KUBE_EDITOR`:

``` 
export KUBE_EDITOR=nano 
kubectl edit pod nginx      <-- Will open nano as defaul editor
```

[More Kubectl commands](Kubectl.md)

---
### vim

Vim is powerfull text editor used by defaul when editing resources via command `kubectl edit`. Knowing how to leave it(`:q!`) and save the changes(`:wq`) is the first thing you should know.

In case you already know the basics, the following shortcuts will help you save some time:

    Mode switch
        i       -> Enter into insert mode 
        ESC     -> exit inset mode (command mode)

    While on command mode (ESC)
        :wq         -> Save and Close file, or ZZ
        :q!         -> quite wihtout saving
        :qa!        -> Close all files, abandon changes
        ZZ          -> Save and exit
        dd          -> Delete current line
        dG          -> Deletes contents from cursor positio to end of file

[vim cheatsheet](https://devhints.io/vim) will give you all shortcuts needed if you want to go beyond the basics.

---
### nano

If *VIM* is too advanced for your, nano might simplify the things, knowing the following shortcuts will save you some time:

> `^` represents `CTRL` on Windows and Linux, or `Command` on Mac

    ^S  -> Save current file
    ^X  -> Close buffer, exit from nano

if nano is your default editor, edit the resource using `kubectl edit pod nginx` then make the desired changes, then `CTRL+S CTRL+X` to save, exit and apply the changes.

[nano cheatsheet](https://www.nano-editor.org/dist/latest/cheatsheet.html) will give you all shortcuts needed to master nano.

---
### grep

---
### cat

The `cat` (“concatenate“) is one of the most used commands in Linux/Unix. `cat` allows us to create a single view of one or multiple files and output the result to the terminal or to a file.

Display the contents of a file in the terminal.  
`cat file.txt`

Display the contents of multiple files in the terminal.  
`cat file1.txt file2.txt`

If the content of the file is too big, use `more` or `less` to paginate the contents.  
`cat longfile.txt | more` (*forwarard only*)  
`cat longfile.txt | less` (*scroll up and down*)  

Create/Replace a file with contents from stdin (press `CTRL+D` to save).  
`cat > file.txt`

Append to a file the contents from stdin (press `CTRL+D` to save).  
`cat >> file.txt`

Allow multiple lines of input to a file until EOF is found.  
```
$ cat <<EOF > file.txt
> a
> b
> c
> EOF
```
Multiline input to a variable
```
$ sql=$(cat <<EOF
SELECT foo, bar FROM db
WHERE foo='baz'
EOF
)
```

---
### tmux

tmux is a terminal multiplexer. It lets you switch easily between several programs in one terminal, detach them (they keep running in the background) and reattach them to a different terminal. It is useful when you have a limited access to only one shell like in the exam terminal.

> `^` represents `CTRL` on Windows and Linux, or `Command` on Mac

    tmux        -> start new session
    ^B          -> enter on command mode

    While on command mode:
        c       -> create console
        n       -> next window
        w       -> window list (selector)
        &       -> kill window
        split panel
        %       -> vertical split
        "       -> horizontal split
        x       -> kill pane
        UP, DOWN-> Switch pane

[tmux cheatsheet](https://gist.github.com/MohamedAlaa/2961058)