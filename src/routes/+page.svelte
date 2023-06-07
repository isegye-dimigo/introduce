<script lang="ts">
    import {onMount} from 'svelte';

    onMount(()=>{
        window.addEventListener('scroll',handleScroll);
    })
    function handleScroll(){
        const header = document.getElementById("header-container");
        const headerText = document.getElementsByClassName("header-element");
        if(header !== null && headerText.length>0) {
            if(window.innerHeight < window.scrollY){
                header.style.backgroundColor = "#0800ff";
                for (let i = 0; i < headerText.length; i++) {
                    (headerText[i] as HTMLElement).style.color = "#ffffff";
                }
            } else{
                header.style.backgroundColor = "#ffffff";
                for (let i = 0; i < headerText.length; i++) {
                    (headerText[i] as HTMLElement).style.color = "#000000";
                }
            }
        }
    }
    const members = [
        {department:"WP",name:"김지훈",imgRoute:""},
        {department:"WP",name:"김강민",imgRoute:""},
        {department:"WP",name:"목정빈",imgRoute:""},
        {department:"WP",name:"임성원",imgRoute:""},
        {department:"EB",name:"피승원",imgRoute:""},
    ];
    const activities = [
        {title:'테스트',desc:'설명'},
        {title:'테스트',desc:'설명'},
        {title:'테스트',desc:'설명'},
        {title:'테스트',desc:'설명'},
    ]
</script>
<header>
    <div id="header-container">
        <a href="#top" class="header-element">=</a>
        <a href="#top" class="header-element">home</a>
        <a href="#club-intro" class="header-element">about</a>
        <a href="#club-member" class="header-element">member</a>
    </div>
</header>
<div id="title-page" class="pages">
    <p id="club-name">ISEKAI</p>
    <canvas></canvas>
</div>
<div id="club-intro" class="pages">
    <div id="desc-box">
        <h2>ISEKAI</h2>
        <p id="club-intro">단편영화 플렛폼 사이트</p>
    </div>
    <div id="gallery">
        {#each activities as activity}
            <div class="gallery-elements">
                <div>{activity.title}</div>
                <div>{activity.desc}</div>
            </div>
        {/each}
    </div>
</div>
<div id="club-member" class="pages">
    <h2>Club member</h2>
    <div id="member-container">
        {#each members as member}
        <div class="member">
            <img src="../img/asdf.png" alt="" srcset="">
            <div>{member.department} {member.name}</div>
        </div>
        {/each}
    </div>
</div>

<style>
    @import '../lib/styles/global.css';
</style>