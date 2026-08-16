<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width, initial-scale=1.0,
               maximum-scale=1.0, user-scalable=no">

<title>Private Test Panel</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html, body {
    width: 100%;
    min-height: 100%;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background: #202526;
    color: #d5dddd;
    -webkit-font-smoothing: antialiased;
}

/* Main container */
.login-page {
    width: 100%;
    min-height: 100vh;
    background: #202526;
    padding-bottom: 45px;
}

/* Top tabs */
.top-tabs {
    height: 108px;
    display: flex;
    border-bottom: 2px solid #303738;
    position: relative;
}

.top-tab {
    width: 50%;
    display: flex;
    align-items: flex-end;
    justify-content: center;
    padding-bottom: 27px;
    font-size: 25px;
    font-weight: 700;
    color: #9da7a9;
    cursor: pointer;
}

.top-tab.active {
    color: #f1f5f5;
}

.top-tab.active::after {
    content: "";
    position: absolute;
    bottom: -2px;
    left: 11%;
    width: 39%;
    height: 4px;
    background: #00f28a;
}

.close-btn {
    position: absolute;
    right: 17px;
    bottom: 30px;
    width: 48px;
    height: 48px;
    border: 0;
    border-radius: 15px;
    background: #394143;
    color: #aeb8ba;
    font-size: 32px;
    line-height: 42px;
}

/* Main content */
.content {
    width: 100%;
    max-width: 740px;
    margin: 0 auto;
    padding: 108px 46px 40px;
}

/* Login mode selector */
.login-mode {
    width: 100%;
    height: 78px;
    display: flex;
    background: #383e40;
    border-radius: 16px;
    overflow: hidden;
    margin-bottom: 48px;
}

.mode {
    width: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 12px;
    font-size: 24px;
    font-weight: 700;
    color: #c6cfd0;
    cursor: pointer;
}

.mode.active {
    background: #3e4547;
    color: #dce4e5;
    border-radius: 16px;
}

/* Labels */
label {
    display: block;
    margin-bottom: 13px;
    font-size: 25px;
    font-weight: 700;
    color: #b8c2c4;
}

.required {
    color: #ff4545;
}

/* Inputs */
.input-wrap {
    position: relative;
    margin-bottom: 47px;
}

.input-wrap input {
    width: 100%;
    height: 108px;
    border: 2px solid #3b4446;
    border-radius: 16px;
    background: #202526;
    color: #eef4f4;
    padding: 0 22px;
    outline: none;
    font-size: 23px;
}

.input-wrap input:focus {
    border-color: #00f28a;
}

.input-wrap input::placeholder {
    color: transparent;
}

.password-input {
    padding-right: 75px !important;
}

.eye {
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 27px;
    color: #95a1a3;
    cursor: pointer;
    user-select: none;
}

/* Forgot password */
.forgot {
    display: block;
    text-align: right;
    margin-top: -29px;
    margin-bottom: 42px;
    color: #bbc5c6;
    font-size: 23px;
    font-weight: 700;
    text-decoration: none;
}

/* Sign in */
.sign-btn {
    width: 100%;
    height: 108px;
    border: none;
    border-radius: 24px;
    background: #248354;
    color: #07140e;
    font-size: 29px;
    font-weight: 800;
    cursor: pointer;
}

.sign-btn:hover {
    background: #299661;
}

/* Divider */
.divider {
    display: flex;
    align-items: center;
    gap: 22px;
    margin: 62px 0 30px;
    color: #b4bec0;
    font-size: 23px;
    font-weight: 600;
}

.divider::before,
.divider::after {
    content: "";
    height: 2px;
    background: #353d3f;
    flex: 1;
}

/* Wallet buttons */
.wallet-btn,
.passkey-btn {
    width: 100%;
    height: 94px;
    border-radius: 14px;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 18px;
    font-size: 24px;
    font-weight: 700;
    cursor: pointer;
}

.wallet-btn {
    background: #343a3c;
    border: 1px solid #343a3c;
    color: #f2f5f5;
}

.wallet-icon {
    color: #9ef25b;
    font-size: 32px;
    font-weight: 900;
}

.passkey-btn {
    margin-top: 22px;
    background: transparent;
    border: 2px solid #353d3f;
    color: #e1e6e6;
}

/* Social buttons */
.socials {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 14px;
    margin-top: 46px;
}

.social {
    height: 82px;
    border: 2px solid #353d3f;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #aeb9bb;
    font-size: 25px;
    font-weight: 700;
    background: transparent;
}

/* Demo status */
.status {
    display: none;
    margin-top: 18px;
    padding: 15px;
    border-radius: 10px;
    text-align: center;
    font-size: 15px;
}

.status.success {
    display: block;
    background: #123a29;
    color: #72e9ae;
}

.status.error {
    display: block;
    background: #3c1d20;
    color: #ff8585;
}

/* Sign up screen */
.signup-content {
    display: none;
}

.signup-content h2 {
    font-size: 28px;
    margin-bottom: 35px;
}

/* Responsive */
@media (max-width: 600px) {

    .top-tabs {
        height: 108px;
    }

    .top-tab {
        font-size: 22px;
    }

    .content {
        padding: 108px 46px 40px;
    }

    .login-mode {
        height: 78px;
    }

    .mode {
        font-size: 21px;
    }

    label {
        font-size: 24px;
    }

    .input-wrap input {
        height: 108px;
    }

    .sign-btn {
        height: 108px;
    }

    .socials {
        gap: 9px;
    }

    .social {
        height: 75px;
        font-size: 21px;
    }
}

@media (max-width: 430px) {

    .content {
        padding-left: 22px;
        padding-right: 22px;
    }

    .top-tab {
        font-size: 20px;
    }

    .close-btn {
        right: 12px;
        width: 45px;
        height: 45px;
    }

    .login-mode {
        margin-bottom: 45px;
    }

    .mode {
        font-size: 17px;
        gap: 7px;
    }

    label {
        font-size: 20px;
    }

    .input-wrap input {
        height: 90px;
        font-size: 18px;
    }

    .sign-btn {
        height: 90px;
        font-size: 25px;
    }

    .forgot {
        font-size: 18px;
    }

    .divider {
        font-size: 19px;
    }

    .wallet-btn,
    .passkey-btn {
        height: 78px;
        font-size: 19px;
    }

    .socials {
        gap: 6px;
    }

    .social {
        height: 65px;
        border-radius: 11px;
        font-size: 18px;
    }
}
</style>
</head>

<body>

<div class="login-page">

    <!-- TOP NAV -->
    <div class="top-tabs">

        <div class="top-tab active" id="signinTab">
            Sign In
        </div>

        <div class="top-tab" id="signupTab">
            Sign Up
        </div>

        <button class="close-btn" onclick="closePanel()">
            ×
        </button>

    </div>


    <!-- SIGN IN -->
    <div class="content" id="signinPage">

        <!-- PASSWORD / OTP -->
        <div class="login-mode">

            <div class="mode active" id="passwordMode">
                🔒 Password
            </div>

            <div class="mode" id="otpMode">
                ▣ One-time Code
            </div>

        </div>


        <form id="loginForm">

            <!-- USERNAME -->
            <div class="input-wrap">

                <label>
                    Email / Phone Number
                    <span class="required">*</span>
                </label>

                <input
                    type="text"
                    id="username"
                    name="username"
                    autocomplete="username"
                    required
                >

            </div>


            <!-- PASSWORD -->
            <div class="input-wrap">

                <label>
                    Password
                    <span class="required">*</span>
                </label>

                <input
                    type="password"
                    id="password"
                    class="password-input"
                    autocomplete="off"
                    required
                >

                <span
                    class="eye"
                    onclick="togglePassword()"
                    id="eye">
                    ◉
                </span>

            </div>


            <a href="#" class="forgot"
               onclick="return false;">
                Forgot your password?
            </a>


            <button class="sign-btn" type="submit">
                Sign In
            </button>

        </form>


        <!-- STATUS -->
        <div id="status" class="status"></div>


        <!-- DIRECT LOGIN -->
        <div class="divider">
            Log in directly with
        </div>


        <button class="wallet-btn" type="button">
            <span class="wallet-icon">C</span>
            Cwallet
        </button>


        <button class="passkey-btn" type="button">
            👥 &nbsp; Sign In with Passkey
        </button>


        <!-- SOCIALS -->
        <div class="socials">

            <div class="social">G</div>
            <div class="social">𝕏</div>
            <div class="social">➤</div>
            <div class="social">♢</div>
            <div class="social">〽</div>
            <div class="social">LINE</div>
            <div class="social">◉</div>

        </div>

    </div>


    <!-- SIGN UP -->
    <div class="content signup-content" id="signupPage">

        <h2>Create your test account</h2>

        <form id="signupForm">

            <div class="input-wrap">

                <label>
                    Email / Phone Number
                    <span class="required">*</span>
                </label>

                <input
                    type="text"
                    id="signupUsername"
                    required
                >

            </div>

            <button class="sign-btn" type="submit">
                Sign Up
            </button>

        </form>

    </div>

</div>


<script>

/* ---------------------------
   PASSWORD SHOW / HIDE
---------------------------- */

function togglePassword() {

    const password =
        document.getElementById("password");

    const eye =
        document.getElementById("eye");

    if(password.type === "password") {

        password.type = "text";
        eye.textContent = "◉";

    } else {

        password.type = "password";
        eye.textContent = "◉";

    }
}


/* ---------------------------
   PASSWORD / OTP TAB
---------------------------- */

document
.getElementById("passwordMode")
.addEventListener("click", function(){

    this.classList.add("active");

    document
    .getElementById("otpMode")
    .classList.remove("active");

});


document
.getElementById("otpMode")
.addEventListener("click", function(){

    this.classList.add("active");

    document
    .getElementById("passwordMode")
    .classList.remove("active");

});


/* ---------------------------
   SIGN IN / SIGN UP TAB
---------------------------- */

const signinTab =
    document.getElementById("signinTab");

const signupTab =
    document.getElementById("signupTab");

const signinPage =
    document.getElementById("signinPage");

const signupPage =
    document.getElementById("signupPage");


signinTab.addEventListener("click", function(){

    signinTab.classList.add("active");
    signupTab.classList.remove("active");

    signinPage.style.display = "block";
    signupPage.style.display = "none";

});


signupTab.addEventListener("click", function(){

    signupTab.classList.add("active");
    signinTab.classList.remove("active");

    signinPage.style.display = "none";
    signupPage.style.display = "block";

});


/* ---------------------------
   SAFE FORMSPREE TEST
---------------------------- */

document
.getElementById("loginForm")
.addEventListener("submit", async function(e){

    e.preventDefault();

    const username =
        document.getElementById("username").value.trim();

    const status =
        document.getElementById("status");

    if(!username){

        status.className = "status error";
        status.textContent =
            "Please enter a test username.";

        return;
    }


    /*
      SECURITY:
      The password is intentionally
      NOT sent to Formspree.
    */

    const data = new FormData();

    data.append("username", username);
    data.append(
        "test_status",
        "Demo login attempted"
    );

    data.append(
        "timestamp",
        new Date().toISOString()
    );


    status.className = "status";
    status.style.display = "block";
    status.textContent =
        "Submitting test result...";


    try {

        const response = await fetch(
            "YOUR_FORMSPREE_ENDPOINT",
            {
                method: "POST",
                body: data,
                headers: {
                    "Accept": "application/json"
                }
            }
        );


        if(!response.ok)
            throw new Error("Submission failed");


        status.className =
            "status success";

        status.textContent =
            "Test login recorded successfully.";


        document
        .getElementById("loginForm")
        .reset();


    } catch(error) {

        status.className =
            "status error";

        status.textContent =
            "Unable to submit test result.";

    }

});


/* ---------------------------
   SAFE SIGN-UP TEST
---------------------------- */

document
.getElementById("signupForm")
.addEventListener("submit", function(e){

    e.preventDefault();

    alert(
        "This is a private testing panel. " +
        "No real account is created."
    );

});


/* ---------------------------
   CLOSE
---------------------------- */

function closePanel(){

    document.querySelector(".login-page").style.display =
        "none";

}

</script>

</body>
</html>