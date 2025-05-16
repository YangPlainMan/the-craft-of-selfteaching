- I already have ssh key, how to use it
	- If you already have an **SSH key**, here’s how to use it with **GitHub** (or other Git services):
	    
---
	- ### **✅ **
	- ### **1. Check if Your SSH Key Exists**
	    
	  Open a terminal and run:  
	    
	  ```
	  ls ~/.ssh
	  ```
	    
	  Look for files like:  
	- id_ed25519 and id_ed25519.pub
	- or id_rsa and id_rsa.pub
	    
	  The file without .pub is the **private key**, and the .pub file is the **public key**.  
	    
---
	- ### **✅ **
	- ### **2. Add Your SSH Key to the SSH Agent**
	    
	  If your key is not already being used, add it manually:  
	    
	  ```
	  eval "$(ssh-agent -s)"
	  ssh-add ~/.ssh/id_ed25519
	  ```
	    
	  Replace id_ed25519 with the correct filename if yours is different.  
	    
---
	- ### **✅ **
	- ### **3. Add Your Public Key to GitHub**
	- Copy your **public key**:
	    
	  ```
	  cat ~/.ssh/id_ed25519.pub
	  ```
	-
	- Go to [GitHub SSH settings](https://github.com/settings/keys)
	- Click **“New SSH key”**
	- Paste the key
	- Give it a title and click **“Add SSH key”**
	    
---
	- ### **✅ **
	- ### **4. Use SSH URL to Clone or Work with Repos**
	    
	  When cloning or working with GitHub repos, use the **SSH URL** (not HTTPS):  
	    
	  ```
	  git@github.com:username/repo-name.git
	  ```
	    
	  Example:  
	    
	  ```
	  git clone git@github.com:octocat/Hello-World.git
	  ```
	    
	  If you already cloned using HTTPS and want to switch to SSH:  
	    
	  ```
	  git remote set-url origin git@github.com:username/repo-name.git
	  ```
	    
---
	- ### **🧪 **
	- ### **Test SSH Connection to GitHub**
	    
	  ```
	  ssh -T git@github.com
	  ```
	    
	  If it’s working, you should see something like:  
	    
	  ```
	  Hi username! You've successfully authenticated, but GitHub does not provide shell access.
	  ```
	    
---
	    
	  If you’re using **Windows**, **WSL**, or a **non-default SSH key file**, let me know — setup steps can be slightly different.