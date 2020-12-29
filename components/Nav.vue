<template>
    <div>
        <b-navbar toggleable="md" type="dark" variant="primary" sticky>
            <div class="container">
                <b-navbar-brand to="/">Learner</b-navbar-brand>

                <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

                <b-collapse id="nav-collapse" is-nav>
                    <b-navbar-nav>
                        <b-nav-item to="/users">Users</b-nav-item>

                        <b-nav-item to="/posts">Posts</b-nav-item>
                    </b-navbar-nav>

                    <b-navbar-nav class="ml-auto">
                        <b-nav-item-dropdown text="User" right>
                            <b-dropdown-item class="text-center" href="#">Profile</b-dropdown-item>

                            <b-dropdown-item class="text-center" href="#">Logout</b-dropdown-item>
                        </b-nav-item-dropdown>
                    </b-navbar-nav>
                </b-collapse>
            </div>
        </b-navbar>
    </div>
</template>
