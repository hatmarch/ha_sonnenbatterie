# ha_sonnenbatterie
Homeassistant integration to show many stats of Sonnenbatterie

Should work with current versions of Sonnenbatterie.

### Tested working with ###
* eco 8.03 9010 ND
* eco 8.0 DE 9010 ND

### Wont work with older Batteries ###
* ex. model 9.2 eco from 2014 not working

### Important: ###
Set the update interval in the Integration Settings. Default is 1 second, which may kill your recorder database

### Install ###
Easiest way is to add this repository to hacs.

#### Alternative Method ####

0. set DEMO_HOME=<root of git repo>
1. Open this in Visual Studio code remote (using the contents of .devcontainer)
2. Follow the instructions [here](https://www.home-assistant.io/docs/installation/virtualenv/#install) for setting up python EXCLUDING step 5
3. Create a config directory under the newly created `homeassistant` directory
4. link to the custom control ln -s custom_components homeassistant/config
5. Outside VS code, run the following from the root of the git repo
```
docker run --init -d --name="home-assistant" -e "TZ=America/Los_Angeles" -v $DEMO_HOME/homeassistant/config:/config -p 8123:8123 homeassistant/home-assistant:stable
```
6. Once it has started successfully, you can shut it down
7. Run the following from the workspace in VSCode container
```
hass --open-ui -c $DEMO_HOME/homeassistant/config
````
8. Once it starts running, make sure you forward the 8081 port out of the container
9. navigate to localhost:8081 (or whatever the port assigned is)
10. After creating login, you should be able to create a sonnenbatterie custom component
11. When initiatlizing the component, you'll need to provide the ip address and password to the local battery api

### Screenshots :) ###
![image](https://user-images.githubusercontent.com/1668465/78452159-ed2d7d80-7689-11ea-9e30-3a66ecc2372a.png)
