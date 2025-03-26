<script>
    let showModal = false;
    let formData = {
        name: '',
        email: '',
        phone: '',
        rating: '',
        message: ''
    };

    function handleSubmit(event) {
        event.preventDefault();
        // Process form data here
        console.log('Form submitted:', formData);
        showModal = true;
    }

    function closeModal() {
        showModal = false;

        formData = {
            name: '',
            email: '',
            phone: '',
            rating: '',
            message: ''
        };
    }
</script>

<div class="form-container">
    <form on:submit={handleSubmit} class="contact-form">
        <h2>Suggest new content!</h2>
        <p>Any idea what we should cover next or what is No Signal Media missing? Don't hesitate and tell us!</p>
        
        <div class="form-row">
            <div class="form-field full-width">
                <label for="name">Your Name</label>
                <input type="text" id="name" bind:value={formData.name} placeholder="Enter your full name" required />
            </div>
        </div>
        
        <div class="form-row">
            <div class="form-field">
                <label for="email">Your Email</label>
                <input type="email" id="email" bind:value={formData.email} placeholder="Enter your email" required />
            </div>
            <div class="form-field">
                <label for="phone">Your Phone</label>
                <input type="tel" id="phone" bind:value={formData.phone} placeholder="Enter your phone number" />
            </div>
        </div>
        
        <div class="form-row">
            <div class="form-field full-width">
                <label>Do you like our website?</label>
                <div class="radio-group">
                    <div class="radio-option">
                        <input type="radio" id="perfection" bind:group={formData.rating} value="perfection" />
                        <label for="perfection">Perfection</label>
                    </div>
                    <div class="radio-option">
                        <input type="radio" id="great" bind:group={formData.rating} value="great" />
                        <label for="great">It's great</label>
                    </div>
                    <div class="radio-option">
                        <input type="radio" id="okay" bind:group={formData.rating} value="okay" />
                        <label for="okay">It's okay</label>
                    </div>
                    <div class="radio-option">
                        <input type="radio" id="needs-improvement" bind:group={formData.rating} value="needs-improvement" />
                        <label for="needs-improvement">Needs improvements</label>
                    </div>
                    <div class="radio-option">
                        <input type="radio" id="hate" bind:group={formData.rating} value="hate" />
                        <label for="hate">I hate it</label>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="form-row">
            <div class="form-field full-width">
                <label for="message">Your Message</label>
                <textarea id="message" bind:value={formData.message} placeholder="Type your message here..." rows="5" required></textarea>
            </div>
        </div>
        
        <div class="form-row">
            <button type="submit" class="submit-button">Submit</button>
        </div>
    </form>
</div>

{#if showModal}
<div class="modal">
    <div class="modal-content">
        <h3>Thank you for your submission!</h3>
        <img src="/logo.gif" alt="No Signal Media logo">
        <button on:click={closeModal} class="close-modal">Close</button>
    </div>
</div>
{/if}

<style>
    .modal {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: black;
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 10;
    }

    .modal-content {
        background-color: #000000;
        padding: 2rem;
        text-align: center;
        border-radius: 15px;
        max-width: 500px;
        width: 90%;
    }
    .modal-content > img{
        width:100%;
        height:auto;
        margin: 1.5rem 0 1.5rem;
    }
    .modal-content h3 {
        font-size: 1.5rem;
        margin-bottom: 1rem;
    }

    .close-modal {
        align-items: center;
        padding: 0.9rem 2.5rem;
        border: none;
        border-radius: 10px;
        border: 1px solid white;
        background-color: black;
        color: rgb(255, 255, 255);
        font-size: 1.1rem;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.3s ease;
        box-shadow: 0 5px 15px rgba(255, 255, 255, 0.2);
        position: relative;
        overflow: hidden;
    }

    .close-modal:hover {
        color: black;
        background-color: #ffffff;
        transform: translateY(-3px) scale(1.2);
        box-shadow: 0 10px 20px rgba(255, 255, 255, 0.2);
    }

    .close-modal:active {
        transform: translateY(1px);
    }

    .form-container {
        max-width: 800px;
        margin: 5vh auto;
        padding: 2rem;
        border-radius: 30px;
        background-color: rgb(0, 0, 0);
        box-shadow: 0 0 25px rgba(255, 255, 255, 0.5);
        position: relative;
        overflow: hidden;
        z-index: 10;
    }

    .contact-form {
        display: flex;
        flex-direction: column;
        gap: 1.5rem;
    }

    .contact-form h2 {
        color: white;
        text-align: center;
        margin-bottom: 1.5rem;
        font-size: 2rem;
        text-shadow: 0 2px 10px rgba(255, 255, 255, 0.2);
    }

    .contact-form p {
        color: white;
        text-align: center;
        margin-bottom: 1.5rem;
        font-size: 1.5rem;
        text-shadow: 0 2px 10px rgba(255, 255, 255, 0.2);
    }

    .form-row {
        display: flex;
        justify-content: center;
        gap: 1.5rem;
        width: 100%;
    }

    .form-field {
        flex: 1;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .full-width {
        width: 100%;
    }

    label {
        color: white;
        font-weight: 500;
        letter-spacing: 0.5px;
        font-size: 0.9rem;
        text-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
    }

    input, textarea {
        padding: 0.8rem 1rem;
        border-radius: 8px;
        border: 1px solid rgb(255, 255, 255, 0.7);
        background: rgba(0, 0, 0, 0.2);
        color: white;
        font-size: 1rem;
        transition: all 0.3s ease;
        box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
    }

    input:focus, textarea:focus {
        outline: none;
        box-shadow: 
            0 0 5px rgba(255, 0, 0, 0.3),
            0 0 10px rgba(255, 251, 0, 0.3),
            0 0 15px rgba(72, 255, 0, 0.3),
            0 0 20px rgba(0, 255, 213, 0.3),
            0 0 25px rgba(0, 43, 255, 0.3),
            0 0 30px rgba(122, 0, 255, 0.3),
            0 0 35px rgba(255, 0, 200, 0.3);
        transform: translateY(-2px);
    }

    .radio-group {
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
        margin-top: 0.5rem;
    }

    .radio-option {
        display: flex;
        align-items: center;
        gap: 1rem;
    }

    .radio-option input[type="radio"] {
        appearance: none;
        width: 18px;
        height: 18px;
        border: 2px solid rgba(255, 255, 255, 0.3);
        border-radius: 70%;
        background: transparent;
        padding: 0;
        position: relative;
        cursor: pointer;
    }

    .radio-option input[type="radio"]:checked {
        border-color: #ffffff;
    }

    .radio-option input[type="radio"]:checked::before {
        content: '';
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 10px;
        height: 10px;
        border-radius: 70%;
        background: #ffffff;
    }

    .radio-option label {
        cursor: pointer;
    }

    textarea {
        resize: vertical;
        min-height: 120px;
    }

    .submit-button {
        align-items: center;
        padding: 0.9rem 2.5rem;
        border: none;
        border-radius: 10px;
        border: 1px solid white;
        background-color: black;
        color: rgb(255, 255, 255);
        font-size: 1.1rem;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.3s ease;
        box-shadow: 0 5px 15px rgba(255, 255, 255, 0.2);
        position: relative;
        overflow: hidden;
    }

    .submit-button:hover {
        color: black;
        background-color: #ffffff;
        transform: translateY(-3px) scale(1.2);
        box-shadow: 0 10px 20px rgba(255, 255, 255, 0.2);
    }

    .submit-button:active {
        transform: translateY(1px);
    }

    @media (max-width: 768px) {
        .form-row {
            flex-direction: column;
            gap: 1rem;
        }

        .form-container {
            margin: 3vh 1rem;
            padding: 1.5rem;
        }

        .radio-group {
            flex-direction: column;
            align-items: flex-start;
        }
    }
</style>
