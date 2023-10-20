<script>
	import axios from 'axios';
	import '@picocss/pico';
    import '../app.css'
	let files;
    let loading = false;
	async function uploadFiles() {
        loading = true;
		const formData = new FormData();
		for (let i = 0; i < files.length; i++) {
			formData.append('files', files[i]);
		}
		try {
			const response = await axios.post('https://pumped-tarpon-promptly.ngrok-free.app/archive', formData);
			console.log(response.data); // signedURL that triggers download.
            loading = false
            window.open(response.data, '_blank');
		} catch (error) {
			console.error('Error uploading files:', error);
		}
	}
</script>

{#if loading}
<div class="main-container">
	<div class="center-container">
		<h1>Archive Creation</h1>
		<a href="/" aria-busy="true">Creating Archive.zip</a>
	</div>
</div>

{:else}
    <div class="main-container">
        <div class="center-container">
            <h1>Archive Creation</h1>
            <input type="file" bind:files multiple />
            <button on:click={uploadFiles}>Upload Files</button>
        </div>
    </div>
{/if}


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