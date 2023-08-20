<template>
    <nav class="navbar">
        <ul>
            <li v-for="(section, idx) in sections" :key="idx" :class="{ active: activeSectionIndex === idx }">
                <a :href="`#${section.id}`">
                    <i :class="section.icon"></i>
                </a>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    data() {
        return {
            sections: [
                { id: 'home', icon: 'las la-home' },
                { id: 'about', icon: 'las la-user' },
                { id: 'my-proj', icon: 'las la-grip-vertical' },
                { id: 'stack', icon: 'las la-sitemap' },
                { id: 'education', icon: 'las la-school' }
            ],
            activeSectionIndex: 0
        };
    },
    methods: {
        updateActiveSection(entries) {
            // console.log(entries);
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const index = this.sections.findIndex(section => section.id === entry.target.id)
                    if (index !== -1) {
                        this.activeSectionIndex = index;
                    }
                }
            });
        }
    },
    mounted() {
        const options = {
            rootMargin: '0px',
            threshold: 0.5
        }

        const observer = new IntersectionObserver(this.updateActiveSection, options)

        this.sections.forEach(section => {
            const element = document.getElementById(section.id)
            if (element) {
                observer.observe(element)
            }
        })
    }
}
</script>
