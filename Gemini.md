## \*:App

```jsx
import "./App.css";
import Main from "./Components/Gemini clone/Main/Main";
import Sidebar from "./Components/Gemini clone/Sidebar/Sidebar";

function App() {
  return (
    <div className="w-full h-[100vh] bg-[#0a101e]  flex ">
      <Sidebar />
      <Main />
    </div>
  );
}

export default App;
```

## 1:Main

```jsx
import MainContent from "./MainContent";
import Navbar from "./Navbar";

function Main() {
  return (
    <div className="font-[Outfit] bg-[#0a101e] flex-1 relative pb-[15vh] min-h-[100vh]  ">
      {/* Navbar */}
      <Navbar />

      {/* MainContent */}
      <MainContent />
    </div>
  );
}

export default Main;
```

## 2:SideBar

```jsx
import { assets } from "../images/assets.js";

function Sidebar() {
  return (
    <div className="md:hidden block">
      <div className="bg-[#1b1b1b] min-h-[100vh] px-[15px] py-[25px] inline-flex flex-col justify-between ">
        {/* Top */}
        <div>
          {/* Menu icon */}
          <img
            src={assets.dark_menu}
            alt="menu"
            className="w-5 block ml-[10px] cursor-pointer"
          />

          {/* New Chat */}
          <div className="bg-[#161616] mt-[50px] px-[15px] py-[10px] inline-flex items-center gap-2 text-sm text-gray-500 rounded-full cursor-pointer">
            <img src={assets.dark_plus} alt="add" className="w-5" />
          </div>
        </div>
        {/* Bottom */}
        <div className="flex flex-col items-center gap-[15px] ">
          {/* Items */}

          {[
            assets.dark_question,
            assets.dark_history,
            assets.dark_settings,
          ].map((item, i) => {
            return (
              <div key={i}>
                <img src={item} alt="help" className="w-5" />
              </div>
            );
          })}

          {/* <div>
          <img src={assets.dark_question} alt="help" className="w-5" />
        </div> */}
        </div>
      </div>
    </div>
  );
}

export default Sidebar;
```

## 3:Main Content

```jsx
import Card from "./Card";
import Greet from "./Greet";
import Input from "./Input";

function MainContent() {
  return (
    <div className="max-w-[900px] m-auto">
      {/* Greet */}
      <Greet />

      {/* Cards */}
      <div className="grid grid-cols-4 p-5 gap-[15px] md:grid-cols-2 sm:flex  sm:flex-col sm:gap-4">
        <Card />
      </div>

      {/* Input */}
      <Input />
    </div>
  );
}

export default MainContent;
```

## 4:NavBar

```jsx
import { assets } from "../images/assets";

function Navbar() {
  return (
    <div className="bg-[#0a101e]  border-b border-b-slate-500/20 p-5 flex text-slate-50 justify-between items-center text-[22px]">
      {/* Text-Logo */}
      <p className="text-transparent bg-gradient-to-r from-slate-100 to-purple-300 bg-clip-text">
        FootprintAI
      </p>

      {/* Profile img */}
      <img
        src={assets.profile_image}
        alt="profile"
        className="w-10 rounded-full"
      />
    </div>
  );
}

export default Navbar;
```

## 5:Greet

```jsx
const Greet = () => {
  return (
    <div className="my-[50px] text-[56px] text-slate-100 p-5 font-medium">
      <p>
        <span className="text-transparent bg-gradient-to-r from-blue-500 to-red-500 bg-clip-text">
          Hello, Footprint
        </span>
      </p>
      <p>How can i help you today?</p>
    </div>

    // className="text-transparent bg-cover bg-norepeat "
    // style="background-image: url('../assets/images/art-145.jpg')"
  );
};

export default Greet;
```

## 6:Card

```jsx
import { assets } from "../images/assets";

const data = [
  {
    paragraph: "Suggest good places to see on upcoming road trip",
    image: assets.dark_compass,
  },
  {
    paragraph: "Briefly summarize this concept: afro style",
    image: assets.dark_message,
  },
  {
    paragraph: "Brainstorm team bonding activities for our coming tour",
    image: assets.dark_bulb,
  },
  {
    paragraph: "Imporove readability of the following code",
    image: assets.dark_code,
  },
];

function Card() {
  return (
    <>
      {data.map((item, i) => {
        return (
          <div
            key={i}
            className="bg-[#1b1b1b]/30 backdrop-blur-md border-r border-slate-500/50  border-b border-b-slate-500/20 hover:bg-slate-700 h-[200px] p-[15px] rounded-lg relative cursor-pointer text-slate-50 border-t border-t-slate-500  border-l border-l-slate-500/20 shadow-xl shadow-black/30"
          >
            {/* Paragraph */}
            <p>{item.paragraph}</p>

            {/* image */}
            <img
              src={item.image}
              alt="compass"
              className="w-[35px] absolute p-[5px] bg-[#0a101e] right-[10px] bottom-[10px] rounded-full"
            />
          </div>
        );
      })}
    </>
  );
}

export default Card;
```

## 7:Input

```jsx
import { assets } from "../images/assets";

function Input() {
  return (
    <div className="w-full max-w-[900px] px-5 m-auto absolute bottom-0">
      {/* Search Box */}
      <div className="flex items-center justify-between gap-5 bg-[#1b1b1b] rounded-[50px] px-5 py-2.5">
        <input
          type="text"
          placeholder="Enter your prompt here"
          className="p-2 flex-1 text-lg border-none outline-none bg-transparent"
        />

        {/* Send icon */}
        <div className="flex items-center gap-[15px]">
          <img
            src={assets.dark_gallery}
            alt="image search"
            className="w-[24px] cursor-pointer"
          />
          <img
            src={assets.dark_mic}
            alt="sound"
            className="w-[24px] cursor-pointer"
          />
        </div>
      </div>

      {/* Bottom info */}
      <p className="text-[13px] my-[15px] mx-auto text-center font-light text-[#585858]">
        FootprintAI may display inaccurate info including people, so
        double-check its responses.Your privacy and Gemini Apps
      </p>
    </div>
  );
}

export default Input;
```

<!--With Light mode dark Mode Concept -->

```jsx
import { assets } from "../../Assets/images/assets";
import { useState } from "react";

const Navbar = () => {
  const [isDark, setIsDark] = useState(true);

  const toggleDarkMode = () => {
    setIsDark(!isDark);
  };

  return (
    <div
      className={`transition-[1s] ${isDark ? "bg-[#0a101e]" : "bg-slate-50"}`}
    >
      <div
        className={`bg-transparent  border-b border-b-slate-500/20 p-5 flex  text-slate-50 justify-between  items-center text-[22px]`}
      >
        {/* Text  Logo*/}
        <p className="text-transparent bg-gradient-to-r from-slate-100  to-purple-300 bg-clip-text">
          FootprintAI
        </p>
        {/* Profile  img*/}
        <img
          src={assets.profile_image}
          alt="profile"
          className="w-10 rounded-full"
          onClick={toggleDarkMode}
        />
      </div>
    </div>
  );
};

export default Navbar;
```
