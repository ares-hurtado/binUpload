<script>
    import '@picocss/pico'
    import '../app.css'
</script>

<div class="main-container">
    <div class="center-container">
        <h1>Archive Creation</h1>
        <form action="pumped-tarpon-promptly.ngrok-free.app/archive" method="POST" enctype="multipart/form-data">
            <input type="file" name="files" multiple>
            <button type="submit">Upload</button>
        </form>
    </div>
</div>

<style>
    .main-container {
        display: flex;
        height: 100vh;
        justify-content: center;
        align-items: center;
    }
    .center-container h1{
        font-size: 4rem;
    }
    button {
        width: 100%;
    }
</style>