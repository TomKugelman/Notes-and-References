Knfie command:
    - knife cookbook create apache — to create cookbook
    - knife cookbook upload apache — to upload cookbook to chef-server
    - knife node run_list add NODENAME “recipe[NAME]” — to add receipe as a runlist to node
    - knife ssh 'name:<nodename>' 'sudo chef-client' -x <user> --sudo - Will execute cookbooks form run_list on that client