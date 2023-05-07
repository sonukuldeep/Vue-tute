
# Vue App

This project uses Vue framework and tailwindcss and is made as a result of my coding adventure with vue framework. 

## Chapter - 1 Basics 
* v-bind alias : example:- v-bind:class, v-bind:href
* v-for example:- v-for="(page,index) in pages"

## Chapter - 2 paging 
* v-on alias @ example:- v-on:click="page = 2", @click="page = 2", @click.prevent="page = 2"

### Playing with css
1. Apply css when value is true. example:- class="cursor-pointer" v-bind:class="{'text-green-400' : activePage == index}"
1. Using computed property. Check video [link](https://www.youtube.com/watch?v=1GNsWa_EZdw&t=46m00s)
1. Using array. example:- :class="[boolean expression ? 'text-green-400' : 'text-white', 'cursor-pointer']"

## Templating 
```js
<main>
    <navbar 
            :pages="pages" 
            :active-page="activePage" 
            :navbar-link="index => activePage = index"></navbar>

    <page-viewer 
        v-bind:page-title="pages[activePage].content"
        v-bind:page-content="pages[activePage].content"></page-viewer>
</main>

<script>
    let app = Vue.createApp({
        data() { // this is state
            return {
                activePage: 0,
                pages: [
                    {
                        link: { text: 'Home', url: 'index.html' },
                        pageTitle: 'Hello from home page',
                        content: 'Hello to vue from home page',
                    },
                    {
                        link: { text: 'About', url: 'about.html' },
                        pageTitle: 'Hello from about page',
                        content: 'Hello to vue from about page',
                    },
                    {
                        link: { text: 'Content', url: 'content.html' },
                        pageTitle: 'Hello from content page',
                        content: 'Hello to vue from content page',
                    },
                ],
            }
        },
    })
    app.component('page-viewer', { // convention to use kabab case
        props: ['pageTitle', 'pageContent',], // notice how i use camel case here and kabab case when i'm passing data
        // we can also pass just page and use page.pageTitle and page.content below
        template: `
            <div class="m-2 p-2">
                <h1 class="text-3xl">{{pageTitle}}</h1>
                <p class="">{{pageContent}}</p>
            </div>
            `
    })
    app.component('navbar', {
        props: ['pages', 'activePage', 'navbarLink'],
        template: `
            <nav class="flex border-b font-bold gap-4 p-4">
                <a v-for="(page,index) in pages" 
                    v-bind:key="index"
                    v-bind:class="[activePage == index ? 'text-green-400' : '', 'cursor-pointer']" 
                    v-bind:href="page.link.url"
                    :title="\`This links to \${page.link.text.toLowerCase()} page\`"
                    v-on:click.prevent="navbarLink(index)">{{page.link.text}}</a>
                <!-- Mark how i use v-for to run a for loop-->
                <!-- Mark the keywork v-bind (alias :) to bind data to attribute  -->
                <!-- v-on has an alias @. Ex @click, @submit etc -->
            </nav>
            `
        })
    app.mount('main')
</script>
```

## Chapter - 3
Using the toolchain i.e vue on vite

Ported chapter 2 to vue on vite 
## Badges

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/) 
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)


## Acknowledgements

 - [Awesome tutorial by ENvato tuts](https://www.youtube.com/watch?v=1GNsWa_EZdw)



## Authors

- [@sonukuldeep](https://www.github.com/sonukuldeepe)


## 🛠 Skills
Javascript, HTML, CSS, Vue, React, Flask
