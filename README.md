# typescript-app-api
small app using express and node. Nothing to see really. I am learning a new language 

Some notes from my learning for the set up 

create a new directory for the ts files
    mkdir src

move to the new directory
    cd ./src

create a file 'app.ts', the ts extension is for the typescript file.
  
launch the new ts file in the editor from the command line.
    code app.ts

add some code to the ts file. 

to compile the ts file and produce the JavaScript (must run insde the src folder):
    tsc app.ts 

look at the app.js file created. Then delete it. 

move to the root folder (assuming still in src):
    cd ..

initialise the typescript complier file. 
    tsc --init

in the tsconfig.json that is created set the output directory to be "./dist"
in the tsconfig.json that is created set the root directory to be "./src"
in the tsconfig.json that is created set the     "moduleResolution": "node",    

now running just 'tsc' in the root directory should result in all .ts files in the ./src directory to be compiled. 

next step is to add node. 

to do this, in the root directory run the command:
    npm init -y

now add a package dependency
    npm i express

now add some development dependency 
    npm i -D typescript ts-node nodemon @types/node @types/express

nodemon is a package that does an auto reload of the code when it is saved. this lets the changes be reflected quickly.
the @types are the files that add the typescript class definitiions for the javascript libraries we will be using. In this case we have pulled down for node js and for express

now open the package.json 

in the scripts section add
    "start": "node dist/app.js",

this tells node that the entry point for the application will be the app.js file. 

now below the start script add a dev and build script:
    "dev": "nodemon src/app.ts",
    "build": "tsc -p ."

the nodemon command is used in dev mode to force the rebuild and reload of the app when a ts file is saved. 
the build command is simply the typescript compiler. 

should now have the commands based on the scripts added: 

    npm run dev

    npm run build 

    npm start 
