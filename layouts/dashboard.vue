<template>
    <div>
        <div class="container-fluid h-100 m-0 p-0" v-resize:throttle="onResize">
            <div class="h-100 row no-gutters">
                <div class="col-auto">
                    <NavDashboardSideNavbar />
                </div>
                <div class="col">
                    <NavDashboardNavbar />
                    <span v-if="user_role == 'Funder'" 
                    class="float-right pr-4 pt-2" style="color: #7FBCFF;">
                        <i class="fas fa-eye"></i> View Only
                    </span>
                    <div class="w-100 h-100 p-3 mt-4">
                        <Nuxt />
                        <!-- <Footer /> -->
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
// import resize from 'vue-resize-directive';
// import roles from '@/assets/roles.json';

export default {
    // provide: function() {
    //     return {
    //         user_role: this.user_role,
    //         page_permissions: this.page_permissions,
    //         checkGroups: this.checkGroups
    //     }
    // },
    data() {
        // return {
        //     roles: roles,
        //     user_role: null,
        //     page_permissions: null
        // }
    },
    directives: {
        resize
    },
    // middleware: ['auth'],
    computed: {
        // getPage() {
        //     return this.$store.state.page_id;
        // }
    },
    created() {
        // this.user_role = this.$auth.user.user_data.groups.length > 0 ? this.$auth.user.user_data.groups[0].name : "None"
    },
    methods: {
        onResize: function () {
            if (this.$store.state.sidebar && window.outerWidth < 768) {
                this.$store.commit('toggleSidebar');
            } else if (!this.$store.state.sidebar && window.outerWidth >= 768) {
                this.$store.commit('toggleSidebar');
            }
        },
        // checkGroups: function (institution=null) {
        //     let that = this;
        //     if (that.$auth.user.user_data.groups.length > 0) {
        //         let user_permissions = that.roles.find(role => role.name == that.$auth.user.user_data.groups[0].name).permissions
        //         let page = user_permissions.find(permission => permission.page == that.$store.state.page_id)

        //         let page_found = page ? true : false
        //         if (page_found && 'institutions' in page && institution) {
        //             page_found = page.institutions.includes(institution);
        //         }

        //         return {page_found: page_found, page_permissions: page_found ? page : null};
        //     } else {
        //         return {page_found: false, page_permissions: null};
        //     }
        // }
    },
};
</script>

<style></style>
