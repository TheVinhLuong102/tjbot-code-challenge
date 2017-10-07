# Text to Speech

TJBot can speak using the speaker and with the help of the [Watson Text to Speech Service](https://ibm.biz/catalog-text-to-speech).

## Create a Watson Text to Speech service

1. Sign up for an IBM Bluemix account at [bluemix.net](https://bluemix.net). If you already have an IBM Bluemix account, sign in.

2. Click on the __Catalog__ link in the top right corner of the Bluemix dashboard.

3. Select the __Text to Speech__ service tile under the __Watson__ section of the catalog.

	![](assets/catalog-tts.png)
	
4. Click on __Create__ to create a service instance.

5. Select __Service Credentials__ in the left sidebar.

	![](assets/sidebar-tts.png)
	
6. Click on __View Credentials__ to display the credentials. Copy the username and password credentials into the `.env` file in the simulator.

	![](assets/servicecredentials-tts.png)
	
.env file

```
TEXT_TO_SPEECH_USERNAME=
TEXT_TO_SPEECH_PASSWORD=
```

## Command TJBot to Speak

For each step, REPLACE the placeholders `/* step ## */` with the suggested code. Do not keep any part of these placeholders in the final code! 

1. First, we create a TJBot object. Here's a template to start with. Copy the template into the `app.js` file in the simulator. 

	```
	var tj = new TJBot(
	  [/* step #2 */],
	  {
	    robot: {
	      gender: "/* step #3 */"
	    },
	    speak: {
	      language: "/* step #4 */"
	    }
	  }, 
	  {
	  	/* step #5 */
	  }
	);
	
	/* step #6 */
	```

1. Enable TJBot to use the speaker hardware by adding the string `"speaker"` as an array element.
	
	```
	var tj = new TJBot(
	  ["speaker"], 
	  {
	    robot: {
	...
	```
	
1. Give the TJBot a gender, `male` or `female`. This will determine the gender of the voice used to synthesize the text.

	```
	...
 	    robot: {
	      gender: "female"
  	    },
	...
	```	    

1. Configure the language TJBot should speak. In this challenge, use `en-US`

	```
	    speak: {
	      language: "en-US"
	    }
	```
	
1. Configure the Watson Text to Speech credentials TJBot should use to speak. Earlier we stored them into an environment variable. 

	```
	  text_to_speech: {
	    username: process.env.TEXT_TO_SPEECH_USERNAME,
	    password: process.env.TEXT_TO_SPEECH_PASSWORD
	  }
	```
	
1. We now have a TJBot configured to speak. Call the `speak` method and have it say `Hello`.

	```
	tj.speak("Hello");	
	```
	
1. Run the code by clicking on the play icon. Did TJBot say hello? You've completed this challenge.