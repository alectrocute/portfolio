<template>
    <div class="h-full-100vh w-full flex flex-col bg-canvas overflow-hidden" :style="cssString">
        <div class="pointer-events-none z-10 absolute w-64 h-64 rounded-full border border-flair-line" :style="state.bio.default ? 'transition: all 350ms ease; top: -128px; left: -125px; opacity: 0.3; transform: scale(1)' : 'transform: all 500ms ease; top: -128px; left: -125px; opacity: 0.3; transform: scale(0.2)'">
        </div>
        <div class="pointer-events-none z-10 absolute w-64 h-64 rounded-full border border-flair-line" :style="state.bio.default ? 'transition: all 500ms ease; top: -128px; left: -125px; opacity: 0.2; transform: scale(-0.9)' : 'transform: all 390ms ease; top: -128px; left: -125px; opacity: 0.2; transform: scale(0.1)'">
        </div>
        <div class="p-2 bg-gray-900">
            <div class="cursor-default text-gray-900 w-full mx-auto flex justify-between p-4">
                <div class="px-2 pr-3 rounded py-2 inline-block flex">
                    <div :class="state.bio.default ? 'relative rounded bg-alec-alt w-8 h-8 overflow-hidden' : 'relative rounded bg-alec-alt w-8 h-8 overflow-hidden'">
                        <img src="../../public/icon.png" :style="'transition: all 220ms ease; transform: translate(' + state.logo.transform + ') scale(' + state.logo.scale + ')'" class="absolute inline-block" />
                    </div>
                    <h1 class="text-alec font-medium my-auto ml-3">Alec Armbruster</h1>
                </div>
                <p style="text-transform: uppercase; letter-spacing: 1.4px" class="text-alec flex justify-start my-auto opacity-50">
                    <svg @click="dark = !dark" xmlns="http://www.w3.org/2000/svg" :class="dark ? 'mr-3 fill-current w-8 h-8 p-2 rounded-full cursor-pointer bg-theme-switch-dark' : 'mr-3 fill-current text-yellow-700 w-8 h-8 p-2 rounded-full cursor-pointer bg-theme-switch-light'" width="24" height="24" viewBox="0 0 20 20">
                        <path style="opacity: .45" d="M7 13.33a7 7 0 1 1 6 0V16H7v-2.67zM7 17h6v1.5c0 .83-.67 1.5-1.5 1.5h-3A1.5 1.5 0 0 1 7 18.5V17zm2-5.1V14h2v-2.1a5 5 0 1 0-2 0z" />
                    </svg>
                    <a v-show="!isMobile" href="https://github.com/alectrocute" target="_blank">
                        <svg xmlns="http://www.w3.org/2000/svg" class="mr-3 fill-current w-8 h-8 p-2 rounded-full bg-alec-lighter border border-icon cursor-pointer hover:shadow" width="24" height="24" viewBox="0 0 24 24">
                            <path style="opacity: .45" d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z" /></svg>
                    </a>
                    <a v-show="!isMobile" href="https://vimeo.com/alecarmbruster" target="_blank">
                        <svg xmlns="http://www.w3.org/2000/svg" class="mr-3 fill-current w-8 h-8 p-2 rounded-full bg-alec-lighter border border-icon cursor-pointer hover:shadow" width="24" height="24" viewBox="0 0 24 24">
                            <path style="opacity: .45" d="M22.875 10.063c-2.442 5.217-8.337 12.319-12.063 12.319-3.672 0-4.203-7.831-6.208-13.043-.987-2.565-1.624-1.976-3.474-.681l-1.128-1.455c2.698-2.372 5.398-5.127 7.057-5.28 1.868-.179 3.018 1.098 3.448 3.832.568 3.593 1.362 9.17 2.748 9.17 1.08 0 3.741-4.424 3.878-6.006.243-2.316-1.703-2.386-3.392-1.663 2.673-8.754 13.793-7.142 9.134 2.807z" /></svg>
                    </a>
                    <a v-show="!isMobile" href="https://facebook.com/alecarmbruster" target="_blank">
                        <svg xmlns="http://www.w3.org/2000/svg" class="mr-3 fill-current w-8 h-8 p-2 rounded-full bg-alec-lighter border border-icon cursor-pointer hover:shadow" width="24" height="24" viewBox="0 0 24 24">
                            <path style="opacity: .45" d="M9 8h-3v4h3v12h5v-12h3.642l.358-4h-4v-1.667c0-.955.192-1.333 1.115-1.333h2.885v-5h-3.808c-3.596 0-5.192 1.583-5.192 4.615v3.385z" /></svg>
                    </a>
                </p>
            </div>
        </div>
        <div class="p-2 bg-gray-900">
            <div class="cursor-default text-alec w-full mx-auto flex justify-between p-4">
                <div class="relative ml-2 w-1/2 inline-block flex">
                    <svg v-if="state.bio.default" class="p-2 fill-current inline-block rounded bg-icon-projects w-8 h-8 mr-2" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 512 512" xml:space="preserve">
                        <g :style="!state.bio.default ? 'transform: scale(1.5)' : 'transform: scale(1)'">
                            <g>
                                <g>
                                    <path d="M509.238,319.765c-9.464-53.081-49.673-99.493-102.441-118.25c-0.042-0.01-1.803-0.625-1.845-0.646
                c-44.368-15.214-78.543-49.372-94.416-95.555C291.9,52.942,245.479,12.751,192.283,2.924
                c-50.997-9.451-152.354,5.7-168.019,21.299C8.631,39.771-6.523,141.129,2.919,192.2c9.849,53.165,50.059,99.556,104.286,118.834
                c44.368,15.214,78.543,49.372,94.406,95.555c18.896,53.081,64.191,92.314,118.231,102.38c11.34,2.115,24.649,3.032,38.75,3.032
                c53.29,0,117.783-13.14,129.164-24.446C503.183,472.205,518.378,371.002,509.238,319.765z M323.719,487.938
                c-45.865-8.542-85.896-43.281-102.542-90.125c-17.365-50.604-56.354-89.573-108.594-107.51
                c-45.313-16.115-80.073-56.125-88.552-101.917c-8.296-44.904,4.303-118.436,12.194-141.958
                C48.706,51.29,68.556,54.52,98.5,59.021c14.885,2.24,31.042,4.667,47.292,7.667c45.823,8.469,85.844,43.208,102.521,90.135
                c17.375,50.594,56.365,89.573,108.594,107.5c45.646,16.219,80.406,56.198,88.542,101.854c3.042,17.073,4.375,29.542,5.542,40.531
                c2.276,21.283,4.091,37.354,15.775,68.275C443.986,483.233,369.052,496.435,323.719,487.938z M480.24,448.517
                c-5.053-16.895-6.4-28.773-8.031-44.069c-1.208-11.344-2.583-24.198-5.76-42.021c-9.458-53.063-49.656-99.458-104.24-118.854
                c-44.333-15.208-78.49-49.354-94.354-95.521c-18.625-52.344-65.01-92.521-118.188-102.344c-16.49-3.042-32.885-5.51-48-7.781
                c-12.371-1.862-26.178-3.945-37.728-6.167c23.141-5.258,58.245-10.438,89.874-10.438c12.427,0,24.292,0.802,34.625,2.708
                c45.823,8.469,85.844,43.219,102.531,90.146c17.365,50.594,56.365,89.573,106.958,106.927l1.625,0.563l0.01,0.01
                c45.646,16.219,80.396,56.198,88.531,101.854C494.708,360.604,487.396,416.669,480.24,448.517z" />
                                    <path d="M333.885,427.167c-18.365-5.823-32.271-19.427-35.438-34.667c-1.208-5.771-6.906-9.469-12.615-8.281
                c-5.771,1.198-9.479,6.854-8.281,12.615c4.781,23.021,23.906,42.438,49.896,50.667c1.073,0.344,2.156,0.5,3.219,0.5
                c4.531,0,8.729-2.906,10.167-7.448C342.615,434.938,339.5,428.948,333.885,427.167z" />
                                    <path d="M309.333,341.333c4.531,0,8.729-2.906,10.167-7.448c1.781-5.615-1.333-11.604-6.948-13.385
                c-18.365-5.823-32.271-19.427-35.438-34.667c-1.208-5.781-6.927-9.49-12.615-8.281c-5.771,1.198-9.479,6.854-8.281,12.615
                c4.781,23.021,23.906,42.438,49.896,50.667C307.188,341.177,308.271,341.333,309.333,341.333z" />
                                    <path d="M184.552,235.167c-18.365-5.823-32.271-19.427-35.438-34.667c-1.208-5.771-6.885-9.479-12.615-8.281
                c-5.771,1.198-9.479,6.854-8.281,12.615c4.781,23.021,23.906,42.438,49.896,50.667c1.073,0.344,2.156,0.5,3.219,0.5
                c4.531,0,8.729-2.906,10.167-7.448C193.281,242.938,190.167,236.948,184.552,235.167z" />
                                    <path d="M163.219,107.167c-5.646-1.802-11.604,1.344-13.385,6.948c-1.781,5.615,1.333,11.604,6.948,13.385
                c18.365,5.823,32.271,19.427,35.438,34.667c1.052,5.042,5.49,8.5,10.438,8.5c0.719,0,1.448-0.073,2.177-0.219
                c5.771-1.198,9.479-6.854,8.281-12.615C208.333,134.813,189.208,115.396,163.219,107.167z" />
                                    <path d="M397.885,363.167c-5.646-1.802-11.604,1.323-13.385,6.948c-1.781,5.615,1.333,11.604,6.948,13.385
                c7.375,2.333,12.906,7.573,14.104,13.333c1.052,5.042,5.49,8.5,10.438,8.5c0.719,0,1.448-0.073,2.177-0.219
                c5.771-1.198,9.479-6.854,8.281-12.615C423.667,379.104,412.719,367.865,397.885,363.167z" />
                                    <path d="M77.885,149.833C70.51,147.5,64.979,142.26,63.781,136.5c-1.219-5.781-6.875-9.458-12.615-8.281
                c-5.771,1.198-9.479,6.854-8.281,12.615c2.792,13.406,13.729,24.646,28.563,29.333c1.073,0.344,2.156,0.5,3.219,0.5
                c4.531,0,8.729-2.906,10.167-7.448C86.615,157.604,83.5,151.604,77.885,149.833z" />
                                </g>
                            </g>
                        </g>
                    </svg>
                    <div v-if="!state.bio.default" class="relative p-2 fill-current inline-block rounded bg-icon w-8 h-8 mr-2 overflow-hidden">
                        <img src="../../public/icon.png" style="left: -10px; top: -3px" class="jump-down absolute inline-block w-32" />
                    </div>
                    <h1 class="text-alec mt-1 ml-2 opacity-50 w-11/12 text-sm" v-html="state.bio.page ? 'about: ' + state.bio.page : 'me in a nutshell'"></h1>
                    <img :class="state.bio.default ? 'absolute w-8 h-8 border border-icon bg-alec p-1 rounded-full avatar avatar-down' : 'absolute w-8 h-8 border border-icon bg-alec p-1 rounded-full avatar avatar-up'" style="top: -18px; left: 18px" src="../../public/me.png">
                    <div :class="state.bio.default ? 'absolute w-6 h-6 rounded border border-icon bg-glass p-1 btn-details btn-details-up' : 'absolute w-10 h-10 border rounded-full border-icon bg-glass p-1 btn-details btn-details-down'" style="top: -12px; left: -12px">
                    </div>
                </div>
            </div>
        </div>
        <div class="pl-6 bg-gray-900 pb-8 text-sm h-48">
            <div class="cursor-default w-full">
                <div v-if="state.bio.default && !isMobile" class="w-full inline-block flex flex-col ml-12">
                    <p class="text-alec w-full">I'm a <span @click="setPage('visual storyteller', skills[0])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">visual storyteller,</span><span @click="setPage('software developer', skills[1])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">software developer,</span><span @click="setPage('musician', skills[2])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">musician</span></p>
                    <p class="text-alec w-full mt-4 sm:mt-5">and <a target="_blank" :href="schoolURL" class="border-b border-icon pb-1 cursor-pointer hover:opacity-75">Ringling</a> grad currently living in <span @click="setPage('location', skills[3])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">Central California.</span></p>
                </div>
                <div v-if="state.bio.default && isMobile" class="w-11/12 inline-block flex flex-col ml-12 leading-loose">
                    <p class="text-alec w-full" style="line-height: 2.8em">I'm a <span @click="setPage('visual storyteller', skills[0])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">visual storyteller,</span><span @click="setPage('software developer', skills[1])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">software developer,</span><span @click="setPage('musician', skills[2])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">musician</span> and <a target="_blank" :href="schoolURL" class="border-b border-icon pb-1 cursor-pointer hover:opacity-75">Ringling</a> grad currently living in <span @click="setPage('location', skills[3])" class="bg-alec-alt p-2 rounded ml-1 cursor-help hover:opacity-75">Central California.</span></p>
                </div>
                <div v-if="!state.bio.default" class="inline-block flex flex-col ml-10 pl-1">
                    <p v-if="isMobile" class="text-alec w-11/12 mb-4 ml-2 leading-loose">{{ state.bio.head }}</p>
                    <p v-if="!isMobile" class="text-alec w-11/12 -ml-3 mb-4 truncate"><span @click="clearPage" class="bg-alec-alt px-2 py-1 rounded cursor-pointer mr-3 hover:bg-canvas hover:opacity-75 text-lg">&larr;</span> {{ state.bio.head }}</p>
                    <p v-if="isMobile" class="text-alec w-11/12 mb-4 truncate"><span @click="clearPage" class="bg-alec-alt px-2 py-1 rounded cursor-pointer mr-3 hover:bg-canvas hover:opacity-75 text-lg">&larr;</span></p>
                    <div v-if="!isMobile" class="flex">
                        <svg class="opacity-75 w-8 h-8 bg-alec p-2 rounded -ml-2 fill-current text-alec" viewBox="0 0 256 282" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMinYMin meet">
                            <g>
                                <path d="M116.504 3.58c6.962-3.985 16.03-4.003 22.986 0 34.995 19.774 70.001 39.517 104.99 59.303 6.581 3.707 10.983 11.031 10.916 18.614v118.968c.049 7.897-4.788 15.396-11.731 19.019-34.88 19.665-69.742 39.354-104.616 59.019-7.106 4.063-16.356 3.75-23.24-.646-10.457-6.062-20.932-12.094-31.39-18.15-2.137-1.274-4.546-2.288-6.055-4.36 1.334-1.798 3.719-2.022 5.657-2.807 4.365-1.388 8.374-3.616 12.384-5.778 1.014-.694 2.252-.428 3.224.193 8.942 5.127 17.805 10.403 26.777 15.481 1.914 1.105 3.852-.362 5.488-1.274 34.228-19.345 68.498-38.617 102.72-57.968 1.268-.61 1.969-1.956 1.866-3.345.024-39.245.006-78.497.012-117.742.145-1.576-.767-3.025-2.192-3.67-34.759-19.575-69.5-39.18-104.253-58.76a3.621 3.621 0 0 0-4.094-.006C91.2 39.257 56.465 58.88 21.712 78.454c-1.42.646-2.373 2.071-2.204 3.653.006 39.245 0 78.497 0 117.748a3.329 3.329 0 0 0 1.89 3.303c9.274 5.259 18.56 10.481 27.84 15.722 5.228 2.814 11.647 4.486 17.407 2.33 5.083-1.823 8.646-7.01 8.549-12.407.048-39.016-.024-78.038.036-117.048-.127-1.732 1.516-3.163 3.2-3 4.456-.03 8.918-.06 13.374.012 1.86-.042 3.14 1.823 2.91 3.568-.018 39.263.048 78.527-.03 117.79.012 10.464-4.287 21.85-13.966 26.97-11.924 6.177-26.662 4.867-38.442-1.056-10.198-5.09-19.93-11.097-29.947-16.55C5.368 215.886.555 208.357.604 200.466V81.497c-.073-7.74 4.504-15.197 11.29-18.85C46.768 42.966 81.636 23.27 116.504 3.58z" />
                                <path d="M146.928 85.99c15.21-.979 31.493-.58 45.18 6.913 10.597 5.742 16.472 17.793 16.659 29.566-.296 1.588-1.956 2.464-3.472 2.355-4.413-.006-8.827.06-13.24-.03-1.872.072-2.96-1.654-3.195-3.309-1.268-5.633-4.34-11.212-9.642-13.929-8.139-4.075-17.576-3.87-26.451-3.785-6.479.344-13.446.905-18.935 4.715-4.214 2.886-5.494 8.712-3.99 13.404 1.418 3.369 5.307 4.456 8.489 5.458 18.33 4.794 37.754 4.317 55.734 10.626 7.444 2.572 14.726 7.572 17.274 15.366 3.333 10.446 1.872 22.932-5.56 31.318-6.027 6.901-14.805 10.657-23.56 12.697-11.647 2.597-23.734 2.663-35.562 1.51-11.122-1.268-22.696-4.19-31.282-11.768-7.342-6.375-10.928-16.308-10.572-25.895.085-1.619 1.697-2.748 3.248-2.615 4.444-.036 8.888-.048 13.332.006 1.775-.127 3.091 1.407 3.182 3.08.82 5.367 2.837 11 7.517 14.182 9.032 5.827 20.365 5.428 30.707 5.591 8.568-.38 18.186-.495 25.178-6.158 3.689-3.23 4.782-8.634 3.785-13.283-1.08-3.925-5.186-5.754-8.712-6.95-18.095-5.724-37.736-3.647-55.656-10.12-7.275-2.571-14.31-7.432-17.105-14.906-3.9-10.578-2.113-23.662 6.098-31.765 8.006-8.06 19.563-11.164 30.551-12.275z" />
                            </g>
                        </svg>
                        <p class="opacity-50 my-auto text-alec ml-4 cursor-pointer truncate w-full h-auto py-2">Did you know? <a target="_blank" :href="ossURL" class="border-gray-900 text-sm border p-2 ml-2 rounded opacity-100 hover:opacity-75 truncate">This website's open source!</a></p>
                    </div>
                </div>
            </div>
        </div>
        <div @click="up(videos[0], 0)" class="ml-2 px-2 pt-2 border-b border-icon-projects">
            <div class="cursor-default w-full mx-auto flex justify-between px-4 py-2 pb-4">
                <div class="w-1/2 inline-block flex text-alec">
                    <svg xmlns="http://www.w3.org/2000/svg" class="px-2 fill-current inline-block rounded bg-icon-projects w-8 h-8 mr-2" viewBox="0 0 24 24">
                        <path class="opacity-50" d="M20 14v4a2 2 0 0 1-2 2h-4v-2a2 2 0 0 0-2-2 2 2 0 0 0-2 2v2H6a2 2 0 0 1-2-2v-4H2a2 2 0 0 1-2-2 2 2 0 0 1 2-2h2V6c0-1.1.9-2 2-2h4V2a2 2 0 0 1 2-2 2 2 0 0 1 2 2v2h4a2 2 0 0 1 2 2v4h-2a2 2 0 0 0-2 2 2 2 0 0 0 2 2h2z" />
                    </svg>
                    <h1 class="text-alec opacity-50 mt-1 ml-2 text-sm">projects</h1>
                </div>
            </div>
        </div>
        <div class="relative h-full w-full flex justify-between overflow-hidden z-10 bg-alec-alt" style="transition: transform 240ms ease-in-out">
            <div class="w-full h-full relative ml-2" :style="!isMobile ? 'top: 50%; left: 0%; transform: translate(0%, 0%)' : ''">
                <div class="cursor-default" v-for="(video, v) in videos" :key="'v#'+v">
                    <div @click="up(video, v)" :style="'z-index: 9999; transform: translateY(-' + step * 100 + '%);'" :class="step == v ? 'my-auto list-trans cursor-pointer flex justify-start p-4 bg-canvas overflow-visible h-20 pl-6' : 'list-trans cursor-pointer flex justify-start p-4 ml-2 h-20'">
                        <div v-show="!isMobile" :class="step == v ? 'shadow relative rounded w-12 h-10 border border-icon overflow-hidden mr-4' : 'relative rounded w-12 h-10 border border-icon bg-alec overflow-hidden mr-4 opacity-50'">
                            <video :class="step == v ? 'video-btn' : 'video-btn opacity-25'" autoplay loop playsinline muted>
                                <source type="video/mp4" :src="video.previewURI" />
                                <source type="video/mp4" :src="video.previewURIMP4" />
                            </video>
                        </div>
                        <div :class="isMobile ? 'font-sm' : 'w-11/12'" @click="up(video, v)" style="z-index: 99">
                            <h1 :class="step == v ? 'text-alec font-medium truncate' : 'text-alec opacity-25 font-medium truncate'">{{ video.title }}</h1>
                            <h1 :class="step == v ? 'text-alec opacity-50 text-sm' : 'text-alec opacity-25 text-sm'"><span :class="isMobile ? 'truncate w-full' : ''">{{ video.desc }}</span></h1>
                        </div>
                    </div>
                </div>
            </div>
            <div class="absolute top-0 right-0 w-1/2 h-full px-8 pb-8 flex flex-col bg-canvas">
                <div class="relative h-64 w-full overflow-hidden mt-8" :style="!isMobile ? 'width: 800px' : 'width: 100%; max-height: 25%'">
                    <video v-if="preview" :src="selVideo.previewURI" class="absolute top-0 left-0 w-full" autoplay loop playsinline muted>
                    </video>
                    <div v-if="!isMobile" class="cursor-default text-alec absolute left-0 bottom-0 px-4 py-4 bg-canvas -ml-2 -mb-4">{{ selVideo.title }}</div>
                </div>
                <div v-if="!isMobile" style="max-width: 800px" class="cursor-default relative w-full py-8 text-alec opacity-75 text-sm px-2 leading-loose"><span :class="isMobile ? 'truncate w-full' : ''">{{ selVideo.description }}</span></div>
                <div class="stats px-2 pb-3 relative bottom-0 left-0 flex justify-start" style="width: 100%; min-width: 250px; max-width: 800px">
                    <div class="flex justify-between w-full">
                        <div v-if="!isMobile" class="cursor-default py-2 text-alec opacity-50 my-auto text-sm">
                            {{ selVideo.desc }}
                        </div>
                        <div class="flex justify-start opacity-50">
                            <div class="h-8 cursor-pointer hover:opacity-75 opacity-100 rounded my-auto py-1 font-medium bg-gray-900">
                                <a target="_blank" :href="selVideo.link" class="text-alec text-sm my-auto bg-alec-alt rounded p-2">External Link
                                    <svg width="25" height="25" viewBox="0 0 25 25" fill="none" xmlns="http://www.w3.org/2000/svg" class="inline-block -mt-1">
                                        <path d="M16.5 13V18.5H6.5V8.5H12" style="stroke: var(--text-alec-primary)"></path>
                                        <path d="M10 15L18.5 6.5" style="stroke: var(--text-alec-primary); opacity: 0.7"></path>
                                        <path d="M14 6.5H18.5V11" style="stroke: var(--text-alec-primary); opacity: 0.7"></path>
                                    </svg>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import { isMobile } from 'mobile-device-detect';
export default {
    data() {
        return {
            step: 0,
            isMobile: isMobile,
            preview: false,
            selVideo: null,
            state: {
                bio: {
                    default: true
                },
                logo: {
                    transform: '0px, -2px',
                    scale: '1.0'
                }
            },
            dark: false,

            themeVar: {
                dark: [
                    { key: null, value: null },
                    {
                        key: 'background',
                        value: '#24f6d114'
                    },
                    {
                        key: 'background-lighter',
                        value: '#08afff0d'
                    },
                    {
                        key: 'background-canvas',
                        value: '#000'
                    },
                    {
                        key: 'background-alternate',
                        value: '#247ef614'
                    },
                    {
                        key: 'text-alec-primary',
                        value: '#24f6d196'
                    },
                    {
                        key: 'gray-alt-1',
                        value: '#0a0a0a'
                    },
                    {
                        key: 'gray-alt-2',
                        value: '#2a2a2a'
                    },
                    {
                        key: 'border-projects',
                        value: 'rgba(255,255,255,0.2)'
                    },
                    {
                        key: 'background-icon',
                        value: 'rgba(255,255,255,0.09)'
                    },
                    {
                        key: 'border-icon',
                        value: 'rgba(255,255,255,0.01)'
                    },
                    {
                        key: 'border-icon-projects',
                        value: 'rgba(255,255,255,0.08)'
                    },
                    {
                        key: 'background-icon-projects',
                        value: 'rgba(255,255,255,0.06)'
                    },
                    {
                        key: 'background-glass',
                        value: 'rgba(255,255,255,0.11)'
                    },
                    {
                        key: 'border-flair-line',
                        value: 'rgba(255,255,255,0.17)'
                    },
                ],
                light: [
                    { key: null, value: null },
                    {
                        key: 'border-icon-projects',
                        value: 'rgba(0,0,0,0.01)'
                    },
                    {
                        key: 'background-icon-projects',
                        value: 'rgba(0,0,0,0.03)'
                    },
                    {
                        key: 'border-flair-line',
                        value: 'rgba(0,0,0,0.2)'
                    },
                    {
                        key: 'background-glass',
                        value: 'rgba(255,255,255,0.8)'
                    },
                    {
                        key: 'background-icon',
                        value: 'rgba(0,0,0,0.1)'
                    },
                    {
                        key: 'border-icon',
                        value: 'rgba(0,0,0,0.11)'
                    },
                    {
                        key: 'border-projects',
                        value: 'rgba(255,255,255,0.1)'
                    },
                    {
                        key: 'background',
                        value: '#fff'
                    },
                    {
                        key: 'background-canvas',
                        value: '#fff'
                    },
                    {
                        key: 'background-lighter',
                        value: 'rgba(0,0,0,0.01)'
                    },

                    {
                        key: 'background-alternate',
                        value: 'rgba(0,10,0,0.015)'
                    },
                    {
                        key: 'text-alec-primary',
                        value: '#000'
                    },
                    {
                        key: 'gray-alt-1',
                        value: '#fff'
                    },
                    {
                        key: 'gray-alt-2',
                        value: '#2a2a2a'
                    },
                ]
            },

            schoolURL: "https://www.ringling.edu",
            ossURL: "https://github.com/alectrocute/portfolio",
            skills: [
                'I write, shoot and edit high-quality video work in fast-turnaround enviorments.',
                'I love Javascript and Python! Websockets and WebRTC are awesome.',
                'I produce analog and digital music, craft sound design and would prefer to be buried with my synths!',
                'Climbing is one of my favorite hobbies. Come visit!'
            ],


            videos: [{
                    previewURI: 'https://alec.work/assets/rtm.webm',
                    previewURIMP4: 'https://alec.work/assets/rtm.mp4',
                    title: 'Right This Minute',
                    desc: 'Appearance',
                    description: 'Right This Minute, a syndicated national American TV show, noticed #boxforyou and actually invited your boii as a guest!',
                    client: 'ABC Disney',
                    link: 'http://www.rightthisminute.com/post/rtmtv-porch-pirate-gets-kitty-litter-surprise-mastermind-joins-rtm',
                    active: true,
                },
                {
                    previewURI: 'https://alec.work/assets/luffa.webm',
                    previewURIMP4: 'https://alec.work/assets/luffa.mp4',
                    title: 'Luffa Gardens',
                    desc: 'Documentary',
                    description: "In 2019 and during my time with Disney ABC Television Group, I shot and edited a little microdocumentary about a Luffa sponge which ended up going really viral... Lesson? People really like sponges.",

                    link: 'https://www.facebook.com/watch/?v=666871803698028',
                    active: false
                },
                {
                    previewURI: 'https://alec.work/assets/boxforyou.webm',
                    previewURIMP4: 'https://alec.work/assets/boxforyou.mp4',
                    title: '#boxforyou',
                    desc: 'Social',
                    description: 'I was living in this beautiful rental in Fresno, California that seemed to have a package black hole on its doorstep. To vent some frustration, I made a really stupid tongue-in-cheek bait box music video.',

                    link: 'https://www.youtube.com/watch?v=wx3JXJqvtIA',
                    active: false
                },
                {
                    previewURI: 'https://alec.work/assets/squarespace.webm',
                    previewURIMP4: 'https://alec.work/assets/squarespace.mp4',
                    title: 'Squarespace',
                    desc: 'Commercial',
                    description: "At four years old, this is definitely one of my older pieces; I still really like it though. I was approached by ad agency @SpecialGuest to contribute cinematography for their 'Build it Beautiful' campaign.",
                    views: '~20,000,000',
                    link: 'https://alec.work/assets/squarespace_preview.mp4',
                    active: false
                },
                {
                    previewURI: 'https://alec.work/assets/backtoschool.webm',
                    previewURIMP4: 'https://alec.work/assets/backtoschool.mp4',
                    title: 'Back To School',
                    desc: 'News Branding',
                    description: "I tried letting genuine stories speak for themselves in a series of brand spots.",
                    views: '~20,000,000',
                    link: 'https://vimeo.com/282587320',
                    active: false
                },

            ]
        }
    },
    mounted() {
        this.preview = false
        this.up(this.videos[0], 0)
    },
    computed: {
        cssString: function() {
            if (this.dark) {
                return this.genCssString(this.themeVar.dark);
            } else {
                return this.genCssString(this.themeVar.light);
            }
        }
    },
    methods: {
        genCssString(o) {
            var r;
            o.forEach(k => {
                r = r + '--' + k.key + ":" + k.value + ";"
            })
            return r;
        },
        setPage(page, content) {
            this.state.bio.page = page
            this.state.bio.head = content
            this.state.bio.default = false

            this.state.logo.scale = '1.2'
            this.state.logo.transform = '0px, 28px) rotate(-45deg'
        },
        logoReset() {
            this.state.logo.scale = '1'
            this.state.logo.transform = '0px, -2px'
        },
        clearPage() {
            this.state.bio.page = null
            this.state.bio.head = null
            this.state.bio.default = true
            this.logoReset()
        },
        up(v, i) {
            this.preview = false
            this.selVideo = v
            this.step = i;
            this.preview = true
        },
    }
}
</script>
<style>
.hide-mobile {
    display: none;
}

.jump-down {
    animation: jump-down 400ms ease-in-out;
    transform: translateY(0px) translateX(0px) rotate(5deg) scale(1.8);
}

@keyframes jump-down {
    from {
        transform: translateY(-20px) translateX(-30px) rotate(30deg) scale(1);
    }

    to {
        transform: translateY(0px) scale(1.8) translateX(0px) rotate(5deg)
    }
}

.border-icon {
    border-color: var(--border-icon);
}

.border-icon-projects {
    border-color: var(--border-icon-projects);
}

.bg-icon-projects {
    background: var(--background-icon-projects);
}

.bg-theme-switch-light {
    background: rgba(255, 255, 0, 0.7);
}

.bg-theme-switch-dark {
    background: rgba(255, 255, 0, 0.15);
}


.border-flair-line {
    border-color: var(--border-flair-line);
}

.avatar {
    transition: all 240ms ease;
    transform: translateY(0px);
    opacity: 1;
}

.avatar-up {
    transform: translateY(-20px) scale(0);
    opacity: 0;
}

.avatar-down {
    transform: translateY(0px) scale(1.0);
    opacity: 1;
}

.btn-details {
    transition: all 240ms ease;
    transform: translateY(0px);
    opacity: 1;
}

.btn-details-up {
    transform: translateY(8px) translateX(-20px) scale(1);
    opacity: 0;
}

.btn-details-down {
    transform: translateY(0px) translateX(0px) scale(1.0);
    opacity: 1;
}

.bg-canvas {
    background: var(--background-canvas)
}

.bg-alec {
    background: var(--background)
}

.bg-alec-lighter {
    background: var(--background-lighter)
}

.bg-alec-alt {
    background: var(--background-alternate)
}

.bg-glass {
    background: var(--background-glass)
}

.border-alec-alt {
    border-color: var(--background-alternate)
}

.border-alec {
    border-color: var(--background);
}

.border-projects {
    border-color: var(--border-projects);
}

.text-alec {
    color: var(--text-alec-primary);
}


.h-full-100vh {
    height: 100vh;
}

.video-btn {
    max-width: none !important;
    position: absolute;
    left: -30%;
    top: -1%;
    margin: 0px auto;
    height: 103%;
    overflow: hidden;
}

.bg-gray-900-2 {
    background: var(--background-canvas);
}


.list-trans {
    transform: translateY(0px);
    transition: transform 200ms ease-in-out;
}

.cursor-help {
    cursor: help;
}

.bg-icon {
    background: var(--background-icon);
}

.bg-gray-900 {
    background: var(--gray-alt-1);
}

.bg-gray-800 {
    background: var(--background-canvas);
}

.bg-gray-700 {
    background: var(--gray-alt-2)
}
</style>
