# Assignment 1

* *Date Created*: 5 FEB 2024
* *Last Modification Date*: 7 FEB 2024
* *Assignment URL*: https://main--assignment1-helpdeskdhrumil.netlify.app/
* *Git URL*: https://git.cs.dal.ca/gosaliya/csci5709-assignments/-/tree/main/Assignment1?ref_type=heads

## Authors

* [Dhrumil Vimalbhai Gosaliya](dh411197@dal.ca)

## Deployment
I deployed on Netlify and made a mirror repository on github from gitlab. The website is operational at the mentioned URL, and Netlify's built-in settings are as needed.


## Built With

* [React](https://legacy.reactjs.org/docs/getting-started.html/) - The web framework used
* [npm](https://docs.npmjs.com//) - Dependency Management

## Sources Used

### home.jsx

*Lines 10 - 20*
```
  const [isChatOpen, setIsChatOpen] = useState(false);

  // Function to open the chat popup
  const openChatPopup = () => {
    setIsChatOpen(true);
  };

  // Function to close the chat popup
  const closeChatPopup = () => {
    setIsChatOpen(false);
  };
```
The code above was created by adapting the code in [Pop up](https://forum.freecodecamp.org/t/what-is-const-isopen-setopen-usestate-false/569764) as shown below: 

```
import React, { usestate } from "react" ; import { NavLink } from "react-router-dom" ;
const Navbar = () = 
const [isOpen, setopen] = useState(false) ;
return (
< nav
className="navbar is-primary" role="navigation" aria-label="main navigation"
‹div className="container">
{/* ...
*/}
</div>
</nav>
) ;
｝；
export default Navbar;
```

*Lines 19 - 32*
```
<div className="chat-modal">
          <div className="chat-modal-content">
            <Chat />
            {/* Close button for the chat popup */}
            <button className="close-button" onClick={closeChatPopup}>
              <FontAwesomeIcon icon={faTimes} />
            </button>
          </div>
</div>
```
The code above was created by adapting the code in [Close button icon](https://fontawesome.com/v5/icons/times?f=classic&s=solid) as shown below: 

```
<FontAwesomeIcon icon={faTimes} />
```

*Lines 44 - 59*
```
function Navbar({ openChatPopup }) {
  return (
    <div className="navbar">
      <div className="brand">FINtastic</div>
      <button className="helpdesk-button" onClick={openChatPopup}>Help Desk</button>
    </div>
  );
}
```
The code above was created by adapting the code in [Navbar](https://getbootstrap.com/docs/4.0/components/navbar/) as shown below: 

```
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Action</a>
          <a class="dropdown-item" href="#">Another action</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Disabled</a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
```

### chat.jsx

*Lines 12 - 46*

```
  useEffect(() => {
    // Send initial messages when the component mounts
    if (location) {
      sendMessage('Hello there! How may I help you?');
      setTimeout(() => sendMessage('What is my balance?'));
      setLocation(false); // Update location to prevent sending messages again
    }
  }, []);

  // Function to get the message text from the input field
  const getMessageText = () => {
    const messageInput = document.querySelector('.message_input');
    return messageInput.value;
  };

  // Function to send a message
  const sendMessage = (text) => {
    if (text.trim() === '') {
      return;
    }

    const messages = document.querySelector('.messages');
    const messageSide = messages.classList.contains('left') ? 'right' : 'left';

    const messageElement = document.createElement('div');
    messageElement.classList.add('message', messageSide);

    const textElement = document.createElement('div');
    textElement.classList.add('text');
    textElement.innerHTML = text;
    messageElement.appendChild(textElement);

    messages.appendChild(messageElement);
    messages.scrollTop = messages.scrollHeight;
  };
```

The code above was created by adapting the code in [Effect hook](https://legacy.reactjs.org/docs/hooks-effect.html) as shown below: 

```
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

*Lines 62 - 75*
```
  return (
    <div className="chat-container">
      <div className="messages" ref={messagesRef}></div>
      <input
        type="text"
        className="message_input"
        placeholder="Type a message..."
        onKeyUp={handleKeyUp}
      />
      <button className="send_message" onClick={handleSendMessageClick}>
        <FontAwesomeIcon icon={faPaperPlane} />
      </button>
    </div>
  );
```
The code above was created by adapting the code in [Paper-plane icon](https://fontawesome.com/icons/paper-plane?f=classic&s=solid) as shown below: 
```
<FontAwesomeIcon icon={faPaperPlane} />
```

## Acknowledgments

* My sincere appreciation goes out to you for the priceless insights and unwavering commitment displayed in the code you provided, which have established a solid foundation for comprehending its complexities and features. 
* Their participation has shaped my understanding of numerous techniques and methodologies and has given me profound insights. Their efforts and knowledge have been invaluable to my development, and I really appreciate them.