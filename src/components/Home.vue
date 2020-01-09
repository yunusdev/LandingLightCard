<template>
    <div class="mt-80" style="">
        <div class="mb-40">
            <hr>
        </div>

        <div class="row" style="margin-bottom: -25px">

            <div class="row col-12">

                <div class="contain3 mb-10">
                    <div class="pull-left">
                        <h2>Payment Information</h2>
                        <p style="color: gray">Choose your method of payment</p>
                    </div>
                    <div class="pull-right">
                        <img style="" class="pr-10" height="26" width="46"  src="../assets/visa.png" alt="">
                        <img style="" class="mr-50" height="40" width="40" src="../assets/discover1.png" alt="">
                        <span  class="dot "></span>
                        <img style=""  height="70" width="90" src="../assets/paypal.png" alt="">

                    </div>
                </div>

            </div>

            <div class="col-12 col-lg-6">

                <div class="">

                    <div id="credit-card" class="contain2 col-lg-9 col-xs-12" style="color: white">

                        <div class=" form-group pt-30">
                            <h6 style="color: white; line-height: 1px;" class="pb-8">CARD NUMBER</h6>
                            <h5 style=" letter-spacing: 4px">{{splitByFour(card.number)}}</h5>
                        </div>

                        <div class="form-group">
                            <img style="" class="sec" src="../assets/sec.jpg" alt="">

                        </div>


                        <div class=" form-group pt-20">
                            <h6 style="color: white; line-height: 1px" class="pb-10">EXPIRATION DATE</h6>
                            <div>
                                <div  class="pull-left">
                                    <h5 style=" letter-spacing: 4px" class="pb-7">{{card.date}}</h5>

                                    <h6 style="font-weight: bold">John Doe</h6>
                                </div>
                                <img style="margin-right: 30px" class="pull-right img-fluid mastercard"   src="../assets/mastercard.png" alt="">
                            </div>
                        </div>


                    </div>


                </div>



            </div>
            <div class="col-12 col-lg-6">

                <div class="row">

                    <div class="col-12 col-md-6 form-group">
                        <label  class="">Credit Card Number</label>
                        <input v-model="card.number" placeholder="4324 5433 9382 1030" class="form-control" type="tel">
                    </div>

                    <div class="col-12 col-md-6 form-group">
                        <label>Expiration  Date</label>
                        <input v-model="card.date" class="form-control" placeholder="03/24" type="text">
                    </div>

                    <div class="col-12 col-md-6 form-group">
                        <label>Security Code</label>
                        <input v-model="card.cvv" placeholder="420" class="form-control" type="text">
                    </div>

                    <div class="col-12 col-md-6 form-group">
                        <label>Postal Code</label>
                        <input v-model="card.postal_code" placeholder="10119" class="form-control" type="text">
                    </div>

                    <div class="col-12 form-group">
                        <label class="radio">
                            <input type="radio" name="r" value="1" >
                            <span style="font-size: 14px">Use this card for the next time purchase</span>
                        </label>

                    </div>

                    <div class="form-group col-12" style="margin-top: -15px">
                        <button class=" btn container btn-info  form-control pt-3 pb-3" style="color: white; border-radius: 6px">Add Card</button>
                    </div>

                </div>

            </div>

        </div>

        <div class="mb-40">
            <hr>
        </div>

        <div class="row" style="">

            <div class="col-12">

                <div class="pull-left">

                    <h4>Subtotal</h4>
                    <h4>Estimated TAX</h4>
                    <h4>Promotional Code: <span style="color: grey">Z4KXLM9A</span></h4>

                </div>
                <div class="pull-right">

                    <h4>N2,4970.00</h4>
                    <h4>N119.64</h4>
                    <h4>-N60.00</h4>
                </div>

            </div>
        </div>

        <div class="mb-40" style="">
            <hr>
        </div>

        <div class="row mb-100">

            <div class="col-12">

                <div class="pull-left col-3" >

                    <button class="btn btn-info form-control pt-3 pb-3 col-12 text-white" style="border-radius: 6px">Complete payment</button>

                </div>
                <div class="pull-right">

                    <h3 style="color: black">Total: N2556.64</h3>

                </div>

            </div>

        </div>

    </div>
</template>

<script>


    export default {
        name: "Home.vue",

        data(){

            return{

                card: {

                    number: this.splitByFour('') || this.splitByFour('4324543393821030'),
                    date: '' || '03/24',
                    cvv: '' || '420',
                    postal_code:  '' || '10119'

                }

            }
        },

        computed: {


        },

        methods: {

            splitByFour(val){

                // var val = $(this).val();
                var newval = '';
                val = val.replace(/\s/g, '');
                for(var i=0; i < val.length; i++) {
                    if(i%4 == 0 && i > 0) newval = newval.concat(' ');
                    newval = newval.concat(val[i]);
                }

                return newval
            }
        }
    }
</script>

<style scoped>
    input{
        background-color: #eee;
        border-radius: 4px;
        border: 1.3px solid #dddddd;
    }

    h4 {

        color: black;
        font-size: 18px;
        margin-bottom: 15px;
    }


    @media (min-width: 767px){

        h6{
            font-size: 13px;
        }

        h5{

            font-size: 15px;
        }
    }

    .mastercard{

        height: 60px;
        width: 90px;
    }

    .sec{

        height: 60px;
        width: 90px;

    }




    @media (max-width: 550px){

        .mastercard{

            height: 30px;
            width: 40px;
        }

        .sec{

            height: 50px;
            width: 70px;

        }


    }




    .btn-info{

        background-color: #3F67EA;
    }
    .contain2{width:100%;padding-right:40px;padding-left:40px;}
    .contain3{width:100%;padding-right:40px;padding-left:7px;}


    hr{

        background-color: #eee;
        border: 0.7px solid #eee;
    }

</style>