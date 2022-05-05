## Using MJML to improve your email in Node-RED

Sending emails with Node-RED is very easy. The email node is easy to configure. Variables can be used in the content area, which we can use to include sensor data, for example.

If you want to send an email in HTML format, there is a lot to consider, because the different email clients have certain expectations about how the HTML code of the email should be structured. To make this task easier, there is MJML. *MJML* stands for Mailjet Markup Language to help developers code emails in a simpler and more efficient way. And to facilitate the use of MJML in Node-RED, I have written a node.

In this article, we will install the node and send a well-structured, beautiful-looking email as an example.

# node-red-contrib-mjml

## Installation

As a requirement, you need to have Node-RED [to be installed](https://nodered.org/docs/getting-started/local). Then change directory to your Node-RED installation and run:

```shell
npm install @vergissberlin/node-red-contrib-mjml
```

**OR** go to your pallet settings in your Node-RED admin UI and search for "mjml".


## Basic template example

Let's now set up a basic flow with which we can send our first mail.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643238680160/CcKIe9xY6.png)

1. Copy and import the following flow into your Node-RED: https://github.com/vergissberlin/node-red-contrib-mjml/blob/main/examples/Parse%20node%20example.json
2. Configure the credentials and receiver address in the email node and press the deploy button
3. Use the button one the debug node to trigger the email proccess.

You will get an email which looks like this:
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1643239000985/yPBbX5I3f.png)

**Pretty cool, right?**

## Deep look into the markup and how to use it

*MJML* has a great [documentation](https://documentation.mjml.io/), and an [online-editor](https://mjml.io/try-it-live/templates/basic) where you can create your email templates easily. There are other pretty fancy looking, ready to use and bulletproof templates available on their [website](https://mjml.io/templates).

MJML is a markup language like HTML and here is the example we use in our flow:

```html
<mjml>
  <mj-body>
    <mj-section>
      <mj-column>
        <mj-image width="100px" src="/assets/img/logo-small.png"></mj-image>
        <mj-divider border-color="#F45E43"></mj-divider>
        <mj-text font-size="20px" color="#F45E43" font-family="helvetica">
            Hello World
        </mj-text>
        <mj-text>
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem 
          Ipsum has been the industry's standard dummy text ever since the 1500s, when 
          an unknown printer took a galley of type and scrambled it to make a type 
          specimen book. It has survived not only five centuries, but also the leap into 
          electronic typesetting, remaining essentially unchanged. It was popularised in the 
          1960s with the release of Letraset sheets containing Lorem Ipsum passages, and 
          more recently with desktop publishing software like Aldus PageMaker including 
          versions of Lorem Ipsum.
        </mj-text>
      </mj-column>
    </mj-section>
  </mj-body>
</mjml>
```

Now we can use variables for sensor data like so:

```html
[…]
        <mj-text>Random number: {msg.payload}</mj-text>
[…]
```

## Summary

Send beautiful, well-structured email with Node-RED is now an easy task to do.
If you like to take a look into the source code, you can do it. It's open source and published on [GitHub](https://github.com/vergissberlin/node-red-contrib-mjml/).

## Links

- [Node-RED repository](https://flows.nodered.org/node/@vergissberlin/node-red-contrib-mjml)
- [Node-RED](http://nodered.org/)
- [MJML documentation](https://documentation.mjml.io/)
- [MJML templates](https://mjml.io/templates)

### Repository on GitHub

%[https://github.com/vergissberlin/node-red-contrib-mjml]
