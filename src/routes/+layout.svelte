<script>
	import { browser } from "$app/environment";
	import Navigation from "$lib/components/Navigation.svelte";
	import "$lib/scss/app.scss";

	if(browser) {
        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry) => {
                if(entry.isIntersecting) {
                    entry.target.classList.add('show');
                    entry.target.classList.remove('hidden');
                }
                else {
                    entry.target.classList.add('hidden');
                    entry.target.classList.remove('show');
                }
            })
        })
        let elements = document.querySelectorAll('.hidden');
        elements.forEach((el) => observer.observe(el));
    }
</script>

<Navigation></Navigation>
<slot />
