this room teaches how to manually review a web application for security issues using only the in-built tools in your browser


* View Source - Use your browser to view the human-readable source code of a website.
* Inspector - Learn how to inspect page elements and make changes to view usually blocked content.
* Debugger - Inspect and control the flow of a page's JavaScript
* Network - See all the network requests a page makes.

## HTML

by inspecting the page, we can view directories in the code.
with the code we can try to move to those directories 
example:
```

                <ul class="nav navbar-nav">
                    <li class="active"><a href="/">Home</a></li>
                    <li><a href="/news">News</a></li>
                    <li><a href="/contact">Contact</a></li>
                    <li><a href="/customers">Customers</a></li>
```

in the HTML people sometimes can leave comments in the page like:
            <p class="welcome-msg">Our dedicated staff are ready <a href="/secret-page">to</a> assist you with your IT problems.</p>

changing the ccs under 
`<div class="premium-customer-blocker">`
  `<h2>Sorry :(</h2>`
  `<h3>This Article Is For Our Premium Customers</h3>`
  `<p>Please talk to a member of staff about upgrading your account today</p>`
  `<a href="/contact" class="btn btn-success">Contact Us</a>`
`</div>`
in the CSS
  display: block; <-----------change to : none;
  position: absolute;
  top: 0;
  left: 0;
  margin-top: 60px;
  width: 100%;
  height: 100%;
  background-color: #FFF;
  border: 2px solid #000;
  text-align: center;
}

once the display: block;  is changed by removing the display: block to none it removes the content blocking the page and showing the contents underneath 

## Debugger
had me use the debugger to use breakpoints and showing how it works 

## Network 

using the network tab and seeing how to use it 

* send the message in the contact while doing that view the response under the network tab inspecting the data 'contact-msg'