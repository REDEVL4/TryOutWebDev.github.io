# TryOutWebDev
<!DOCTYPE html>
<html>

<head>
    <title>project</title>
    <style>
        body {
            background-color: cornflowerblue;
        }
        
        #outer {
            display: flex;
            flex-wrap: wrap;
            background-color: hsl(69, 72%, 70%);
            justify-content: center;
            /* align-items: center; */
            margin-left: auto;
            margin-right: auto;
            margin-top: 12%;
            width: 600px;
            height: 300px;
            padding-top: 30px;
            padding-bottom: 10px;
            border-radius: 18PX;
            border-style: solid;
        }
        
        button {
            display: block;
            margin-left: auto;
            margin-right: auto;
            background-color: slateblue;
            color: #0a1402;
            text-align: center;
            width: 80px;
            height: 30px;
            border-radius: 10px;
        }
        
        p {
            color: coral;
            font-size: 30px;
            font-family: fantasy;
            text-align: center;
            margin-left: auto;
            margin-right: auto;
        }
        
        #p {
            display: block;
            margin-top: 1%;
            color: deeppink;
            text-align: center;
        }
    </style>
</head>

<body>
    <div id="outer">

        <div id="inner">
            <p>Here is your treat</p>
            <p id="p"></p>
            <button id="button">Click Me</button>

        </div>
    </div>
    <script>
        const b = document.getElementById('button');
        const v = document.getElementById("p");

        const callme = async() => {
                try {
                    const setheader = {
                        headers: {
                            Accept: "application/json"
                        }
                    }
                    const response = await fetch('https://icanhazdadjoke.com', setheader);
                    const data = await response.json();
                    v.innerHTML = data.joke;

                } catch (err) {
                    console.log(err);
                }
            }
            // const callme = () => {
            //     const setheader = {
            //         headers: {
            //             Accept: "application/json"
            //         }
            //     };
            //     fetch('https://icanhazdadjoke.com', setheader)
            //         .then((res) => res.json())
            //         .then((data) => {
            //             v.innerHTML = data.joke;
            //         })
            //         .catch((error) => {
            //             console.log(error);
            //         })
            // };
        b.addEventListener('click', callme);
        callme();
        // b.addEventListener('click', () => {
        //     setInterval(() => {
        //         const t = new Date();
        //         v.innerHTML = t.toLocaleTimeString();
        //     }, 1000)
        // });
    </script>
</body>

</html>
