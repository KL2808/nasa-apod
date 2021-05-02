<script>
	import Display from './components/Display.svelte';
	import Header from './components/Header.svelte';
	import config from '../config/config'
</script>

<Header/>
<Display apiKey={config.PRIVAT_API_KEY}/>