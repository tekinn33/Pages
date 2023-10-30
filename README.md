# Pages
import React from "react"
import {Router, Routes, Route, Link} from "react-router-dom"
import { Products } from "./Products"
export const Home = () => {
    return (
        <>
      <div>
        This is home page.
      </div>  
      < Router>
      <button><Link to="Products" />Products</button>
      <button><Link to="Contact" />Contact</button>
      <Routes>
        <Route  path="/Proucts" element={<Products />} />
        <Route  path="/Contact" element={<Contact />} />
      </Routes>
      </Router>   
      </> 
    )
}


import {Router, Routes, Route, Link} from "react-router-dom"
export const Contact = () => {

    const [formData, setFormData] = useState({
        name: '',
        email: '',
        message: '',
      });
    
      const handleChange = (e) => {
        const { name, value } = e.target;
        setFormData((prevData) => ({
          ...prevData,
          [name]: value,
        }));
      };
    
      const handleSubmit = (e) => {
        e.preventDefault();
        // Form submission logic goes here (e.g., send data to server)
        console.log('Form submitted:', formData);
      };
    

    return (
        <>
      <div>
       <h1>Contact With Us</h1>
      </div>   

      <div className="App">
      <header className="App-header">
        <h1>Contact Us</h1>
      </header>
      <section className="contact-form">
        <form onSubmit={handleSubmit}>
          <label htmlFor="name">Name:</label>
          <input
            type="text"
            id="name"
            name="name"
            value={formData.name}
            onChange={handleChange}
            required
          />

          <label htmlFor="email">Email:</label>
          <input
            type="email"
            id="email"
            name="email"
            value={formData.email}
            onChange={handleChange}
            required
          />

          <label htmlFor="message">Message:</label>
          <textarea
            id="message"
            name="message"
            value={formData.message}
            onChange={handleChange}
            required
          ></textarea>

          <button type="submit">Submit</button>
        </form>
      </section>
    </div>

      
      <Router>
        <button><Link to="/"/>Back To Home</button>
        <Routes>
            <Route path="/" element={<Home />}/>
        </Routes>
      </Router>
      </>
    )
}



import Win1 from "./images/Win1"
import Win2 from "./images/Win2"
export const Products = () => {
    return (
        <>
      <div>
        <img src={Win1}/> 
      </div> 

      <div>
        <img src={Win2}/>
      </div>
      </>
    )
}
