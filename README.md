# demo-gn-ninja
# run this repo on linux environment (todo: update for windows)

# Gn gen
gn gen out/test1
gn gen out/test3 --args="is_two_people = false"

# Build
ninja –C [gen_folder] [target name]
ex: ninja -C out/test1 ​all

# Find dependency of a target
gn desc [gen_folder] [target_name]
ex: gn desc out/test1 //helloservice:hello2

# Find which target reference on specific target
gn refs [gen_folder] [target_name]
ex: gn refs out/test1 //helloservice:hello2
