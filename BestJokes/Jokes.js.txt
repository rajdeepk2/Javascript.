
const joke=document.querySelector('#joke');
const jokebtn=document.querySelector('#jokebtn');

    ///////////////////////////////////////////////USING PROMISES////////////////////////////////////////////////////////////////
    //const generatejokes=()=>{
    // const setHeader={
    //     //object set kr rhe hai
    //     headers:{
    //         Accept:"application/json"
    //     }
    // }
    // fetch('https://icanhazdadjoke.com/',setHeader)//sara html content tha isliye setheader m se get kia joke only
    // .then((res)=> res.json())
    // .then((data)=>{
    //     joke.innerHTML=data.joke;
    // })
    // .catch((error)=>{
    //  console.log(error);
    // })
    //}
    ///////////////////////////////////////////////////USING ASYNCAWAIT//////////////////////////////////////
    const generatejokes=async()=>{
        try{
    const setHeader={
                //object set kr rhe hai
                headers:{
                    Accept:"application/json"
                }
            }
    const res=await fetch('https://icanhazdadjoke.com/',setHeader);
    const data=await res.json();
    joke.innerHTML=data.joke;
        }catch(err){
           console.log(`the error is ${err}`);
        }
    }

jokebtn.addEventListener('click',generatejokes);
generatejokes();//for first time koi joke show ho isliye
