<template>
    <div class="wrapper">
        <div class="container">
            <div class="myForm">
                <div>
                    <label for="carName">Vehicle Name</label>
                    <input type="text"
                           id="carName"
                           class="form-control"
                           v-model="carData.name">
                </div>
                <div>
                    <label for="make">Car Make</label>
                    <input type="text"
                           id="make"
                           class="form-control"
                           v-model="carData.make">
                </div>

                <div>
                    <label for="model">Car Model</label>
                    <input type="text"
                           id="model"
                           class="form-control"
                           v-model="carData.model">
                </div>

                <div>
                    <label for="description">Vehicle description</label>
                    <textarea id="description"
                              rows="5"
                              class="form-control"
                              v-model="message"/>
                </div>

                <label for="automatic">
                    <input type="radio"
                           id="automatic"
                           value="Automatic"
                           v-model="transmissionType"> Automatic
                </label>
                <label for="manual">
                    <input type="radio"
                           id="manual"
                           value="Manual"
                           v-model="transmissionType"> Manual
                </label>
                <div>
                    <label for="fuelType">Fuel Type</label>
                    <select id="fuelType"
                            class="form-control"
                            v-model="selectedFuelType">
                        <option disabled>Select Fuel Type</option>
                        <option v-for="(fuelType,index) in fuelTypes" :key="index">{{ fuelType }}</option>
                    </select>
                </div>

                <div class="btnWrapper">
                    <button class="submitBtn" :class="{'is-loading':isSubmitted}"
                            @click.prevent="submitted">Submit
                    </button>
                </div>
            </div>

            <div class="card" v-if="isSubmitted">
                <div class="card-body">
                    <h4 class="card-title">Car Details</h4>
                    <p>Car Name: <b>{{ carData.name }}</b></p>
                    <p>Car Make: <b>{{ carData.make }}</b></p>
                    <p>Car Model: <b>{{ carData.model }}</b></p>
                    <p>Car Transmission: <b>{{ transmissionType }}</b></p>
                    <p>Fuel Type: <b>{{ selectedFuelType }}</b></p>
                    <p>Description: <b>{{ message }}</b></p>
                </div>
            </div>
        </div>
    </div>


</template>

<script>
    export default {
        name: "Home",
        data() {
            return {
                carData: {
                    name: '',
                    make: '',
                    model: '',
                    transmissionType: "",
                    selectedFuelType: ""

                },
                message: 'Describe the vehicle...',
                transmissionType: '',
                selectedFuelType: '',
                fuelTypes: ['Electric', 'Diesel', 'Petrol'],
                isSubmitted: false,
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true;
            }
        },
    }
</script>

<style scoped>

</style>