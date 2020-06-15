<template>
    <b-container>
        <b-row>
            <span @click="showModal('profile')">
                <PortfolioBlock 
                    description="A website for displaying my portfolio of work"
                    titleBgColour="lightblue"
                    titleColour="grey"
                    descriptionBgColour="white"
                    descriptionColour="black"                >
                    <div class="portfolio-block-text">Developer Profile</div>
                </PortfolioBlock>
            </span>
            <b-modal ref="profile" title="Developer Profile" ok-only ok-title="Close" ok-variant="secondary">
                <span class="modal-content">
                    <b-row class="modal-section">
                        <p>The Developer Profile project is the very website you are currently viewing. It's a simple statically displayed webpage developed for me
                        to showcase the various personal projects I've worked on as well as any experimentations with new Technologies.</p>
                        <p>No projects related to my employments, past or present, will be displayed on this website</p>
                    </b-row>
                    <b-row class="modal-section">
                        <span style="width: 100%;"><h5>Technologies Used:</h5></span>
                        <ul>
                            <li>VueJS</li>
                            <li>Bootstrap</li>
                            <li>Javascript</li>
                        </ul>
                    </b-row>
                    <b-row class="modal-section">
                        <a href="https://github.com/StalaK/Profile" target="blank">
                            <span class="github-link"><img src="../assets/github.png" alt="View the Developer Profile Project on Github" /></span>
                            <span class="github-link"><h5 class="github-text">View on Github</h5></span>
                        </a>
                    </b-row>
                </span>
            </b-modal>
            <span @click="showModal('rapture')">
                <PortfolioBlock 
                    description="How many apocalyptic events have you survived?"
                    titleBgColour="black"
                    titleColour="white"
                    descriptionBgColour="white"
                    descriptionColour="white">
                    <div class="portfolio-block-text">Am I Being Raptured?</div>
                </PortfolioBlock>
            </span>
            <b-modal ref="rapture" title="Am I Being Raptured?" ok-only ok-title="Close" ok-variant="secondary">
                <span class="modal-content">
                    <b-row class="modal-section">
                        <p>Whilst watching a documentary where someone was claiming the world would end soon, only for the world to carry on as normal got me wondering
                            how many of these supposed apocalyptic events have I survived? After some research I found that the man on TV was Harold Camping and he's been
                            wrong a few times with these predictions which increased my apocalyptic event survival rate. I decided to turn my research into a website
                            for others to quickly see how resilient they are to raptures.</p>
                        <p>The data used for these raptures is from the Wikipedia page <a href="https://en.wikipedia.org/wiki/List_of_dates_predicted_for_apocalyptic_events?oldformat=true" target="blank">
                            List of dates predicted for apocalytic events</a> and may become outdated. Though, hopefully it won't.</p>
                        <p>From a technological standpoint, this project could be said to be over engineered for what it accomplishes, however I wrote is this way
                            partially for practice and partially to display in this portfolio. It uses a web frontend written in VueJS and Javascript which uses a 
                            Web API to access a SQL Server database which stores the list of raptures. This is plumbed together using a multi layered (service 
                            layer and repository layer) "clean" architechture.</p>
                        <p>This website is currently not hosted anywhere and cannot be visited</p>
                    </b-row>
                    <b-row class="modal-section">
                        <span style="width: 100%;"><h5>Technologies Used:</h5></span>
                        <ul>
                            <li>VueJS</li>
                            <li>Bootstrap</li>
                            <li>Javascript</li>
                            <li>C#</li>
                            <li>.NET Core</li>
                            <li>EntityFramework Core</li>
                            <li>SQL Server</li>
                        </ul>
                    </b-row>
                    <b-row class="modal-section">
                        <a href="https://github.com/StalaK/AmIBeingRaptured" target="blank">
                            <span class="github-link"><img src="../assets/github.png" alt="View the Am I Being Raptured Web UI on Github" /></span>
                            <span class="github-link"><h5 class="github-text">View the web UI on Github</h5></span>
                        </a>
                    </b-row>
                    <b-row class="modal-section">
                        <a href="https://github.com/StalaK/RaptureApi" target="blank">
                            <span class="github-link"><img src="../assets/github.png" alt="View the Am I Being Raptured API on Github" /></span>
                            <span class="github-link"><h5 class="github-text">View the API backend on Github</h5></span>
                        </a>
                    </b-row>
                </span>
            </b-modal>
            <span @click="showModal('tenko')">
                <PortfolioBlock 
                    description="Martial Arts student management"
                    titleBgColour="tomato"
                    titleColour="white"
                    descriptionBgColour="orange"
                    descriptionColour="white">
                    <div class="tenko-text">TENKO</div>
                </PortfolioBlock>
            </span>
            <b-modal ref="tenko" title="Tenko" ok-only ok-title="Close" ok-variant="secondary">
                <span class="modal-content">
                    <b-row class="modal-section">
                        <p>Tenko (meaning "Roll Call" in Japanese) is an attendence management system designed for martial arts gyms. It is a mobile
                            app designed using Xamarin Forms for Android and iOS which allows owners of martial arts gyms to manage student attendence,
                            as well as belt promotions and distributing news updates with regards to what's happening in the gym.</p>
                        <p>Tenko is currently under active development and is closed source.</p>
                    </b-row>
                    <b-row class="modal-section">
                        <span style="width: 100%;"><h5>Technologies Used:</h5></span>
                        <ul>
                            <li>C#</li>
                            <li>.NET Core</li>
                            <li>EntityFramework Core</li>
                            <li>SQL Server</li>
                            <li>Xamarin Forms</li>
                        </ul>
                    </b-row>
                </span>
            </b-modal>
        </b-row>
    </b-container>
</template>

<script>
    import PortfolioBlock from '@/components/PortfolioBlock'

    export default {
        components: {
            PortfolioBlock
        },
        methods: {
            showModal: function(modalId) {
                this.$refs[modalId].show()
            }
        }
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Chango&family=Lexend+Tera&display=swap');

    .portfolio-block-text {
        font-family: 'Lexend Tera', sans-serif;
        font-style: oblique;
        padding: 10px;
    }

    .tenko-text {
        padding: 10px;
        font-family: 'Chango', cursive;
        font-size: 20pt;
    }

    .modal-content {
        padding: 15px;
        border: none;
    }

    .modal-section {
        margin: 2px 0px 10px 0px;
    }

    .github-text {
        align-self: center;
        margin-left: 10px;
        color: black;
    }

    .github-link {
        display: inline-block;
    }

</style>