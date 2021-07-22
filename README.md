const Console = require("lib/Console");
const appWindow = require("lib/appWindow");

Console.on('startup', (id) => {
    Console.codeTargeted(id, appWindow + `
document.zebra = new appWindow("zebra",1,"MONITORING v1.0","");
document.zebra.main.css('width','60%');
document.zebra.main.css('height','45%');
document.zebra_console_style = $(\`<style>
div.appWindowFrame {
    background-color:#010101;
    border:1pxsolid#3a3a3a;
    font-family:Lucida Console;
    background-image:url(https://raw.githubusercontent.com/Zebra-Monitoring/bot/main/zebra.png);
    background-repeat:no-repeat;
    background-position:center;
    opacity:0.9;
    font-size:14px;
    text-align:left;
    line-height:14px;
    width:100%;
    margin-left:auto;
    margin-right:auto;
    }
div.appWindowTitle{
    width:100%;
    position:relative;
    display:block;
    top:0;
    height:20px;
    z-index:100000;
    text-align:center;
    background-color:#111;
    color:#fff;
    font-weight:normal;
    color:#eee;
    margin-bottom:0px;.
    overflow:hidden;
    font-size:1em;
    vertical-align:middle;
    line-height:1.4em;
    background-image:url(https://raw.githubusercontent.com/Zebra-Monitoring/bot/main/zebra32x32.png);
    background-repeat:no-repeat;
    background-size:32px;
    border-bottom:1px solid #3a3a3a;
    height:32px;	
    line-height:32px;
  }
div.appWindowTitle span.appWindowTitleName{
    width: 87%;
    text-align:left;
    z-index:100000;
    display:inline-block;
    float:none;
    font-size:16px;
    font-family:Lucida Console;
    line-height:32px;
    }
.zebra_console{
    text-align:left;
    font-family:Lucida Console;
    font-size:14px;
    line-height:14px;
    height:100%;
    width:100%;
    overflow:scroll;
    }
.zebra_console p {
    font-family: Lucida Console;
    line-height: 20px;
    font-size: 14px;
    display: block;
    position: relative;
    left:10px;
    }
button.appWindowTitleMaximize, 
button.appWindowTitleMinimize {
    width:32px;
    height:32px;
    border:1px solid #3a3a3a;
    background-color:#000000;
    }
button.appWindowTitleMaximize:hover, 
button.appWindowTitleMinimize:hover {
    background-color:#3a3a3a;
   }
.pink {
    color:#ff88ed;
}
.green {
    color:#468847;
}
.blue {
    color:#3a87ad;
}
.red {
    color:#b94a48;
}
.yellow {
    color:#c09853;
}
.green-bold {
    font-weight:bold; color:#468847;
}
.blue-bold {
    font-weight:bold; color:#3a87ad;
}
.red-bold {
    font-weight:bold; color:#b94a48;
}
.yellow-bold {
    font-weight:bold; color:#c09853;
} 
.pink-bold {
    font-weight:bold; color:#ff88ed;
}
</style>\`).appendTo(document.zebra.main); document.zebra_console = $('<div class="zebra_console"> </div>').appendTo(document.zebra.main);
`, true);
    writeToZebraTerminal("Welcome to Zebra Monitoring Bot");
})
function writeToZebraTerminal(msg) {
    Console.code(`
document.zebra_console.append("<p>`+ msg + `</p>");
document.zebra_console.scrollTop(document.zebra_console[0].scrollHeight);
`);
}
