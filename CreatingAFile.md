# React Starting Guide
## Getting Started
1. Clone the repository https://github.com/WilsonHacks-Competition-Team/SyntHacksTodo.git
2. Open the **SyntHacksTodo** Folder in a new **VSCode** window
3. Open a new terminal window and type `npm i`
4. Open the **src** then **components** folders
5. Create a new folder with your name as the title
6. Inside that folder create an **index.js** file
## New File
Open your index.js file and at the top add the following import statements:

    import  React, {Component} from  'react'
    import { withRouter } from  'react-router-dom';

Next create a class using the following format replaceing **ClassName** with **YourName** (ex: mine would be **Maxwell**):

    export  default  class  ClassName  extends  Component {
    
    }

Then, inside your class we need to make a constructor. Add the following code: 

    constructor(props) {
	    super(props)
	    this.state = {
		    title: "Maxwell", //add your name here
		}
    }

After that you need to add a render function. Add the following code under your constructor: 

    render() {
	    return(
		    <h1>{this.state.title}</h1>
		)
	}
Lastly, we have to add the page to the navigation bar and the routes constants. First open the **constants** folder and then the **routes.js** file. In there, add the following to the bottom:

    export const YOURNAME = "/yourname"; 
    //the first one should be in all caps with the second one all lower case

Next open **App** and then **index.js**. At the top, add 

    import  YourName  from  '../YourName';

Then in the render funcition, below TestPage. Add the following:

    <Route  exact  path={ROUTES.YOURNAME}  component={YourName}/>
Lastly, open the **Navigation** folder and then **index.js**. In **index.js**, scroll down to the **NavigationNonAuth** constant and add the following under **Test**:

    // Test part
    <li
	    style={Object.assign({},linkStyle.liLeft, linkStyle.li)}
	>
		<Link  to={ROUTES.TEST}  style={linkStyle.link}>Test</Link>
	</li>
	// Under here add this
	<li
	    style={Object.assign({},linkStyle.liLeft, linkStyle.li)}
	>
		<Link  to={ROUTES.YOURNAME}  style={linkStyle.link}>YourName</Link>
	</li>
## Running your App
Now if you open your terminal and type `npm start` your browser should open after a couple of seconds. Then select **YourName** at the top of the page and you should see your page show up.
