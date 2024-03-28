<template>
    <div class="login-form vh-100">
        <div class="container py-5 h-100">
            <div class="d-flex align-items-center justify-content-center h-100">
                <form>
                    <div class="form-outline mb-4">
                        <label for="username">Gebruikersnaam:</label>
                        <input type="text" class="form-control form-control-lg" id="username" required />
                    </div>
                    <div class="form-outline mb-4">
                        <label for="password">Wachtwoord:</label>
                        <input  class="form-control form-control-lg" id="password" required />
                    </div>
                    <div class="d-flex justify-content-around align-items-center mb-4">
                        <!-- Checkbox -->
                        <div class="form-check">
                            <input class="form-check-input" type="checkbox" value="" id="rememberme" checked />
                            <label class="form-check-label" for="rememberme">
                                Remember me
                            </label>
                        </div>
                    </div>

                    <!-- Submit button -->
                    <button type="submit" class="btn btn-primary btn-lg btn-block w-100">
                        Sign in
                    </button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
    };
  }
};
</script>

<style scoped lang="scss">
    form {
        min-width: 400px;
    }
</style>
