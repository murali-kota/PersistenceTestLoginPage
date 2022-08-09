

<template>
  <div>
    
        <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);-ms-transform: translate(-50%, -50%);-webkit-transform: translate(-50%, -50%);">
            <div class="row">
                <div class="col-md-7" style="padding-right: 0;">
                    <div class="panel panel-default js-login-panel" style="height: 400px;">
                        <div class="panel-body">
                            <div class="login-form">
                                <div class="center-block" style="max-width: 66%; margin-top: 20px; margin-bottom: 20px;">
                                <img id="" src="/assets/images/Onclusive_ForwardPlanner_Logo.svg" alt="Product Logo" />                                
                                </div>
                                <form>
                                   <div class="form-group">
                                      <label>Username</label>
                                        <input id="input-email" v-model="email" class="form-control" type="email" placeholder="Enter email" />                                 
                                    </div>
                                    <div class="form-group">
                                      <label>Password</label>
                                      <input id="input-password"  v-model="password" class="form-control" placeholder="Enter Password" type="password" > 
                                    </div>
                                    <div class="form-group pull-right">
                                        <span class="checkbox-inline"><input id="cphBody_loginMain_chkRememberMe" type="checkbox" name="ctl00$cphBody$loginMain$chkRememberMe" /><label for="cphBody_loginMain_chkRememberMe">Remember Me</label></span>
                                    </div>
                                    <div class="form-group">
                                        <input type="submit" name="ctl00$cphBody$loginMain$Button1" value="Log In" class="btn btn-planner"/>
                                    </div>
                                    <p v-if="errors.length">
                                      <b>Please correct the following error(s):</b>
                                      <ul>
                                        <li v-for="error in errors">{{ error }}</li>
                                      </ul>
                                    </p>
                                    <div class="success" v-if="isSuccess">We received your submission, thank you!</div>
                                </form>

                    <div id="cphBody_divSupport">
                        <p class="text-center">
                            <a href="ForgotPassword.aspx">Reset password</a>
                            <span class="inline-seperator"> | </span>
                            <a href="/pages/Contactus">Contact Support</a>
                        </p>
                    </div>
                    
                    <div>
                        <p class="text-center">
                            <small class="help-block">
                                By logging in, you agree to our <a href="pages/Terms">Terms of Service</a> and <a href="pages/Privacy">Privacy Policy</a>.
                            </small>
                        </p>
                    </div>
                            </div>
                        </div>
                    </div>
                     
                </div>
                <div class="col-md-5 hidden-xs hidden-sm" style="padding-left:0;">
                    <div class="panel panel-default m-b-n js-twitter-panel" style="height: 400px; overflow: auto; width: 300px;">
                        <div class="panel-body" style="padding: 0;">
                            <a class="twitter-timeline" href="https://twitter.com/Tracy_Planning?ref_src=twsrc%5Etfw">Tweets by Tracy_Planning</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
                        </div>
                    </div>
                </div>
              
            </div>
        </div>
    
  </div>
</template>
<style>

</style>
<script>


export default {
  name: "LoginForm",
  components: {    
  },
  data() {
    return {
      loading: true,      
      email: "",
      password: "",
      message: "",
      errors:[],
      isSuccess: false
    };
  },

  methods: {
      onSubmit(event) {
         let data = {
        password: this.name,
        email: this.email             
      };
      this.errors = [];
      alert(`Form has been submitted - ${this.email} ${this.password}`);
      if(this.email.length == 0)
      {
        this.errors.push("Please enter email");
      }
      if(data.password.length == 0)
      {
        this.errors.push("Please enter password");
      }
      if(!data.email.includes("@"))
      {
        this.errors.push("Please enter valid email");
      }
      if(this.errors.length > 0) 
      {
        return false;
        event.preventDefault();
      }
      this.isSuccess=true;
      alert(`Form has been submitted - ${JSON.stringify(this.form)}`);
    },      
  },
};
</script>

