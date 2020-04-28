# lirc config files

This is HOW-TO repository to create a new remote control config file for lirc.

# 1. Use the following command to create only the protocol specific information. ie no keys are added.

$irrecord -f 

# 2. Capture the raw codes for each key

$ ir-ctl -r<file_name> -1

# 3. Copy all raw codes of keys to common directory (usefull to apply the sed command)

# 4. Remove pulse, space and newlines

$ find . -type f -exec sed -i 's/pulse//g' {} ';'

$ find . -type f -exec sed -i 's/space//g' {} ';'

$ find . -type f -exec sed -i 's/^ //g' {} ';'

$ find . -type f -exec sed -i ':a;N;$!ba;s/\n//g' {} ';'

# 5. Copy all the raw codes in config file.
