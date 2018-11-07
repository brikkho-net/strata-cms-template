---
date: 2016-12-22T20:04:40.407Z
title: Create new components in ReactJS
---
The instructions are:
Create TWO new components: UserInput and UserOutput
<iframe width="100%" height="475" src="https://stackblitz.com/edit/react-udv7og?embed=1&file=Components/UserInput.js" frameborder="0"></iframe> 

UserInput should hold an input element, UserOutput two paragraphs
Output multiple UserOutput components in the App component (any paragraph texts of your choice)
Pass a username (of your choice) to UserOutput via props and display it there
Add state to the App component (=> the username) and pass the username to the UserOutput component
  state = {
    persons: [
      { name: "Tyrell", age: 38 },
      { name: "Tyrone", age: 28 },
      { name: "Ty", age: 18 }
    ],
     username: '',
     password: ''
  };
Add a method to manipulate the state (=> an event-handler method)

Pass the event-handler method reference to the UserInput component and bind it to the input-change event
 userNameChangedHandler = (event) => {
    this.setState({ 
          username: event.target.value 
    })
  }

  passwordChangedHandler = (event) => {
    this.setState({
      password: event.target.value
    })
  }
Ensure that the new input entered by the user overwrites the old username passed to UserOutput

Add two-way-binding to your input (in UserInput) to also display the starting username
 <UserInput
                 changed1 = {
                   this.userNameChangedHandler
                 }

                 changed2 = {
                   this.passwordChangedHandler
                 }

                 username = {
                   this.state.username
                 } 
                 password = {
                   this.state.password
                 }
                 />
                 <br />
                  < UserOutput 
                  username = {
                    this.state.username
                  }
                  password = {
                    this.state.password
                  }
                  />
Add styling of your choice to your components/ elements in the components - both with inline styles and stylesheets
const style = {
        backgroundColor: '#4CAF50',
        border: 'none',
        color: 'white',
        padding: '15px 32px',
        textAlign: 'center',
        textDecoration: 'none',
        display: 'inline-block',
        fontSize: '16px'
    }
    
Inside of your button component, you can now reference your style.
 <button style={style} onClick={this.switchNameHandler}>Switch Name</button>
<iframe width="100%" height="475" src="https://stackblitz.com/edit/react-udv7og?embed=1&file=App.js" frameborder="0"></iframe> 

