<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-md-6 col-md-offset-3">
                <h1 style="text-align: center; font-weight: bold;">{{ title }}</h1>
            </div>
        </div>
        <div class="row" style="padding: 30px;">
            <div class="col-md-6 col-md-offset-4">
                <div class="col-md-8">
                    <vue-cloneya :minimum="1"  :value="exampleData" v-on:minimum:cloneya="alert('min')" v-on:maximum:cloneya="alert('max')">
                        <div class="input-group" style="margin-top: 10px;">
                            <input type="text" name="example[]" class="form-control" placeholder="Example" v-cloneya-input>
                            <span class="input-group-btn">
                                <button type="button" class="btn btn-success clonspan" tabindex="-1" v-cloneya-add><i class="fa fa-plus"></i></button>
                                <button type="button" class="btn btn-danger delete" tabindex="-1"  v-cloneya-remove><i class="fa fa-minus"></i></button>
                            </span>
                        </div>
                    </vue-cloneya>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "App",
        data: () => {
            return {
                title: 'Vue Cloneya',
                exampleData: [
                    'Vue',
                    'Cloneya',
                    'VueCloneya Example',
                    'More than min'
                ]
            }
        },
        mounted() {
            setTimeout(() => {
                this.exampleData.reverse();
                alert('Example data reversed');
            }, 5000);
        },
        methods: {
            alert(msg) {
                alert(msg);
            }
        }
    }
</script>

<style scoped>

</style>