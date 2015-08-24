# Load ~/.extra, ~/.bash_prompt, ~/.exports, ~/.aliases and ~/.functions
# ~/.extra can be used for settings you don’t want to commit
for file in ~/.{extra,bash_prompt,exports,aliases,functions}; do
	[ -r "$file" ] && source "$file"
done
unset file

# Add tab completion for SSH hostnames based on ~/.ssh/config, ignoring wildcards
[ -e "$HOME/.ssh/config" ] && complete -o "default" -o "nospace" -W "$(grep "^Host" ~/.ssh/config | grep -v "[?*]" | cut -d " " -f2)" scp sftp ssh

# Allow to pip install only if there is a virtualenv currently activated
export PIP_REQUIRE_VIRTUALENV=true
# But create a function to allow the use of system pip with syspip command
syspip(){
     PIP_REQUIRE_VIRTUALENV="" pip "$@"
   }

# Ensure user-installed binaries take precedence (like homebrew's)
export PATH=/usr/local/bin:$PATH

