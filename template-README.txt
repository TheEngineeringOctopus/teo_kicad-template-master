When using this template repo, can't use Githubs built-in template system (it ignores the submodule).
Instead follow these directions - https://help.github.com/en/github/creating-cloning-and-archiving-repositories/duplicating-a-repository

1) Make a new blank repo at https://github.com/new (without using a template)

2) Open Git Bash. Create a bare clone of the template repository;

git clone --bare git@github.com:TheEngineeringOctopus/teo_kicad-template-master.git TEMP_TEO_kicad-template

3) Mirror-push this bare clone to the new blank Github repository;

cd TEMP_TEO_kicad-template
git push --mirror git@github.com:TheEngineeringOctopus/TEOXXXX.git

(you might need to run:  ```eval "$(ssh-agent -s)"''' and ``` ssh-add.exe ~/.ssh/TEO/id_ed25519'''


4) Remove the temporary local repository you created earlier;

cd ..
rm -rf TEMP_TEO_kicad-template

5) Then clone the new templated PCB design as normal from Github!

6) Run ```git submodule update --init''' to pull the submodule lib contents
