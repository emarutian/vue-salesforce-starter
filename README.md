# vue-salesforce-starter

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

## Prepare the build for Salesforce Deployment


### create vue.config.js file as specified -> add the section below with publicPath: '/'

```
module.exports = {
  publicPath: './'
};
```

### Build the project 
```
npm run build
```
### go to DIST folder and create an archive (zip) file from the contents -> archive these files

![Archive the contents of the dist folder](https://user-images.githubusercontent.com/1533929/65367876-4e5d9a00-dbed-11e9-99bf-33d80c2053b8.png)


## Prepare the Salesforce. 

### Create a new static resource

Go to salesforce, setup, type "static resources " in quick find. Create a new static resource with options as shown below and upload the contents of the archived build from the previous step. and click "save".

![New Static Resource Creation](https://user-images.githubusercontent.com/1533929/65367910-e0fe3900-dbed-11e9-8518-767a2af3b584.png)

### Create a new lightning web component using SF Developer Console where the vue app will reside

#### Open Salesforce Developer Console and create a new Lightning component as shown on the picture

![SF Developer Console - Creating Web Component](https://user-images.githubusercontent.com/1533929/65367946-713c7e00-dbee-11e9-9771-489e51a9334e.png)

#### Fill out the options as shown for the new component
![Fill out the options as shown](https://user-images.githubusercontent.com/1533929/65367955-9204d380-dbee-11e9-96bf-50d286fc7e83.png)

#### Configure the vueApp.cmp file
Copy paste the below line as shown on the picture below to specify the static resource folder that was created before ("vue") and the entry point (the "/index.html").
```
<lightning:container src="{!$Resource.vue + '/index.html'}"/>
```
![Lightning Component Configuration](https://user-images.githubusercontent.com/1533929/65367973-dbedb980-dbee-11e9-8042-b9c44a19a0df.png)

### Let's use the component

Let's say we decided to put the component on the "Home" page..

#### Goto "Edit page" as shown on the picture below

![SF Edit Home Page](https://user-images.githubusercontent.com/1533929/65368012-2d964400-dbef-11e9-92bc-eb0c47f3fee0.png)

#### Find the newly created component on the left under "Custom" and drag it onto a section of the screen

You should be able to preview the component after that as shown below
![Drag and Drop the vue component](https://user-images.githubusercontent.com/1533929/65368017-3be46000-dbef-11e9-9f8b-0189517af09c.png)

#### Save the changes and exit the edit mode
Click "Activate" to activate the changes and select the default visibility options when prompted as shown below. Then click "save"

![Save and Activate the changes made](https://user-images.githubusercontent.com/1533929/65368024-68987780-dbef-11e9-9973-e388abd12511.png)

![Accept the default options](https://user-images.githubusercontent.com/1533929/65368032-aa292280-dbef-11e9-9191-c54a846b14ba.png)

#### That's it! You should be able to see the Vue starter page inside Salesforce

![Vue Starter Page inside Salesforce](https://user-images.githubusercontent.com/1533929/65368044-d775d080-dbef-11e9-8940-aa2df4b34216.png)

