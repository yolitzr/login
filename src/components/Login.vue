<template>
    <div class="container">
        <div class="form-container">
            <div class="sing-in-sing-up">
                <form action="login" class="sign-in-form">
                    <h2 class="title">Sign in</h2>
                    <div class="input-field">
                        <i class="fas fa-user"></i>
                        <input type="text" name="user" placeholder="Username">
                    </div>
                    <div class="input-field">
                        <i class="fas fa-lock"></i>
                        <input type="password" name="password" placeholder="Password">
                    </div>
                    <input type="submit" value="Login" class="btn solid">
                    <p class="social-text">Or Sign in with social platforms</p>
                    <div class="social-media">
                        <a href="#" class="social-icon">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="social-icon">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="social-icon">
                            <i class="fab fa-google"></i>
                        </a>
                        <a href="#" class="social-icon">
                            <i class="fab fa-linkedin-in"></i>
                        </a>
                    </div>
                </form>

                <form action="login" class="sign-up-form">
                    <h2 class="title">Sign up</h2>
                    <div class="input-field">
                        <i class="fas fa-user"></i>
                        <input type="text" name="user" placeholder="Username">
                    </div>
                    <div class="input-field">
                        <i class="fas fa-envelope"></i>
                        <input type="text" name="mail" placeholder="Email">
                    </div>
                    <div class="input-field">
                        <i class="fas fa-lock"></i>
                        <input type="password" name="password" placeholder="Password">
                    </div>
                    <input type="submit" value="Sign Up" class="btn solid">
                    <p class="social-text">Or Sign up with social platforms</p>
                    <div class="social-media">
                        <a href="#" class="social-icon">
                            <i class="fab fa-facebook-f"></i>
                        </a>
                        <a href="#" class="social-icon">
                            <i class="fab fa-twitter"></i>
                        </a>
                        <a href="#" class="social-icon">
                            <i class="fab fa-google"></i>
                        </a>
                        <a href="#" class="social-icon">
                            <i class="fab fa-linkedin-in"></i>
                        </a>
                    </div>
                </form>
            </div>
        </div>

        <div class="panel-container">
            <div class="panel panel-left">
                <div class="content">
                    <h3>New here?</h3>
                    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, impedit.</p>
                    <button class="btn transparent" id="sign-up-btn" @click="signUp">Sign Up</button>
                </div>
                <img src="../assets/login.svg" class="panel-img" alt="">
            </div>

            <div class="panel panel-right">
                <div class="content">
                    <h3>One of us</h3>
                    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, impedit.</p>
                    <button class="btn transparent" id="sign-in-btn" @click="signIn">Sign in</button>
                </div>
                <img src="../assets/register.svg" class="panel-img" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Login',
    methods: {
        signUp: function () {
            const container = document.querySelector('.container');
            container.classList.add("sign-up-mode");
        },

        signIn: function () {
            const container = document.querySelector('.container');
            container.classList.remove("sign-up-mode");
        },
    }
}
</script>

<style scoped>
.container {
    position: relative;
    width: 100%;
    min-height: 100vh;
    background-color: #fff;
    overflow: hidden;
}

.container:before {
    content: '';
    position: absolute;
    top: 5%;
    right: 50%;
    width: 1800px;
    height: 1800px;
    border-radius: 50%;
    background: linear-gradient(-45deg, #FD93DB, #fa75d0);
    transform: translateY(-50%);
    transition: 1.8s ease-in-out;
    z-index: 6;
}

.form-container {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
}

.sing-in-sing-up {
    position: absolute;
    top: 50%;
    left: 75%;
    transform: translate(-50%, -50%);
    width: 50%;
    display: grid;
    grid-template-columns: 1fr;
    z-index: 5;
    transition: 1s 0.7s ease-in-out;
}

form {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    grid-column: 1 / 2;
    grid-row: 1 / 2;
    padding: 0 4rem;
    overflow: hidden;
    transition: 0.2s 0.6s ease-in-out;
}

form.sign-up-form {
    z-index: 1;
    opacity: 0;
}

form.sign-in-form {
    z-index: 2;
}

.title {
    font-size: 2rem;
    color: #444;
    margin-bottom: 10px;
}

.input-field {
    max-width: 380px;
    width: 100%;
    height: 50px;
    background-color: #f0f0f0;
    margin: 10px 0;
    border-radius: 50px;
    display: grid;
    grid-template-columns: 15% 85%;
    padding: 0 .4rem;
}

.input-field i {
    text-align: center;
    line-height: 50px;
    color: #acacac;
    font-size: 1rem;
}

.input-field input {
    background: none;
    outline: none;
    border: none;
    font-weight: 400;
    font-size: 1rem;
    color: #7e7474;
}

.input-field input::placerholder {
    color: #7e7a7a;
    font-weight: 300;
}

.btn {
    width: 150px;
    height: 45px;
    border: none;
    outline: none;
    border-radius: 50px;
    cursor: pointer;
    background-color: #FD93DB;
    color: #fff;
    font-weight: 600;
    letter-spacing: .1rem;
    text-transform: uppercase;
    margin: 10px 0;
    transition: .5s;
}

.btn:hover {
    background-color: #fa75d0;
}

.social-text {
    padding: .8rem 0;
    font-size: 1rem;
    letter-spacing: .05rem;
}

.social-media {
    display: flex;
    justify-content: center;
    align-items: center;
}

.social-icon {
    height: 45px;
    width: 45px;
    border: 1px solid #FD93DB;
    border-radius: 50%;
    margin: 0 0.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1rem;
    text-decoration: none;
    transition: .4s;
}

.social-icon:hover {
    color: #fa75d0;
    border: 1px solid #fa75d0;
}

.panel-container {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
}

.panel {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    justify-content: space-around;
    text-align: center;
    z-index: 6;
}

.panel-left {
    pointer-events: all;
    padding: 3rem 17% 2rem 12%;
}

.panel-right {
    pointer-events: none;
    padding: 3rem 12% 2rem 17%;
}

.panel .content {
    color: #fff;
    transition: .9s .6s ease-in-out;
}

.panel h3 {
    font-weight: 600;
    font-size: 1.5rem;
}

.panel p {
    font-size: 0.95rem;
    padding: 0.5rem 0;
}

.btn.transparent {
    background: none;
    border: 2px solid #fff;
    width: 140px;
    height: 45px;
    font-weight: 600;
    font-size: 0.8rem;
}

.panel-img {
    width: 100%;
    transition: 1.8s .5s ease-in-out;
}

.panel-right .content, .panel-right .panel-img {
    transform: translateX(800px);
}

/* Animacion */
.container.sign-up-mode:before {
    transform: translate(100%, -50%);
    right: 52%;
}

.container.sign-up-mode .panel-left .panel-img,
.container.sign-up-mode .panel-left .content {
    transform: translateX(-800px);
}

.container.sign-up-mode .panel-right .panel-img,
.container.sign-up-mode .panel-right .content {
    transform: translateX(0px);
}

.container.sign-up-mode .panel-left {
    pointer-events: none;
}

.container.sign-up-mode .panel-right {
    pointer-events: all;
}

.container.sign-up-mode .sing-in-sing-up {
    left: 25%;
}

.container.sign-up-mode .sign-in-form {
    z-index: 1;
    opacity: 0;
}

.container.sign-up-mode .sign-up-form {
    z-index: 2;
    opacity: 1;
}
</style>
