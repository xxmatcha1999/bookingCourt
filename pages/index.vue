<template>
    <div>
         <div class="all">
      <v-row >
        <v-col cols="9" sm="8" md="8">
          <div class="tag-bar-heade">
            <div class="heade-blog">
            <div
              style="
                width: 5px;
                height: 40px;
                border-radius: 1px;
                background-color: rgb(3, 155, 229);
                float: left;
              "
            >
              <div
                style="
                  font-size: 16px;
                  color: rgb(255, 255, 255);
                  width: 50rem;
                  line-height: 40px;
                  float: left;
                  padding-left: 2rem;
                "
              >
                ข้อมูลลูกค้า
              </div>
            </div>
          </div>
          <v-form>
            <v-container>
              <div class="col-xs-12" style="margin-top: 3rem; margin-bottom: 2rem">
            <div class="heade-flex">
              <div class="row">
                <div class="col-xs-12 col-md-6 col-lg-6" style="text-align:center">
                  รูป
                </div>
                <div class="col-xs-12 col-md-6 col-lg-6">
                  กลุ่มลูกค้า
                      <div class="" style="position:relative" >
                          <button type="button" :class="cho ==true ? 'btn-customer' : 'btn-customer-choose'" @click="switchCa">apple</button>
                          <button type="button" :class="cho2 ==true ? 'btn-customer' : 'btn-customer-choose'" @click="switchCb" style="margin-left:-20px">banana</button>
                      </div>
                      <div>
                        <v-radio-group
                          v-model="row"
                          row
                        >
                          <v-radio
                            label="All rent"
                            value="radio-1"
                          ></v-radio>
                          <v-radio
                            label="One time"
                            value="radio-2"
                          ></v-radio>
                        </v-radio-group>
                      </div>
                </div>
              </div>
              <div class="row">
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-autocomplete
                    ><template slot="label">
                        ประเภทนิติบุคคล<a class="req">*</a
                        ><v-autocomplete></v-autocomplete></template
                    ></v-autocomplete>
                </div>
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-autocomplete
                    ><template slot="label">
                        Subsidiary<a class="req">*</a
                        ><v-autocomplete></v-autocomplete></template
                    ></v-autocomplete>
                </div>
              </div>
              <div class="row">
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      ชื่อนิติบุคคล <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-autocomplete
                    ><template slot="label">
                        ประเภทลูกค้า<a class="req">*</a
                        ><v-autocomplete></v-autocomplete></template
                    ></v-autocomplete>
                </div>
              </div>
              <div class="row">
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      Tax ID <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      Sale Rep <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
              </div>
              <div class="row">
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      E-mail <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text>ประเภทภาษีเงินได้หัก ณ ที่จ่าย</v-text><br>
                  <v-radio-group
                          v-model="row"
                          row
                        >
                          <v-radio
                            label="สินค้า"
                            value="r1"
                          ></v-radio>
                          <v-radio
                            label="บริการ"
                            value="r2"
                          ></v-radio>
                          <v-radio
                            label="อื่นๆ"
                            value="r3"
                          ></v-radio>
                        </v-radio-group>
                  </div>
              </div>
              <div class="row">
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      เบอร์โทร <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      โปรดระบุ <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
              </div>
              <div class="row">
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      Fax<a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-xs-12 col-md-6 col-lg-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    hide-details="auto"
                    ><template slot="label">
                      <span class="icon-Store iconic1-member" style="padding-right: 5px"></span>
                      เอกสารเพิ่มเติม <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
              </div>
              
            </div>
            <div class="col-xs-12" style="padding: 0px; margin-bottom: 1rem">

            </div>
            </div>
            </v-container>
          </v-form>
          </div>
        </v-col>
        <v-col cols="3" sm="4" md="4">
          <div class="tag-bar-heade">
            <div class="heade-blog">
            <div
              style="
                width: 5px;
                height: 40px;
                border-radius: 1px;
                background-color: rgb(3, 155, 229);
                float: left;
              "
            >
              <div
                style="
                  font-size: 16px;
                  color: rgb(255, 255, 255);
                  width: 50rem;
                  line-height: 40px;
                  float: left;
                  padding-left: 2rem;
                "
              >
                ที่อยู่
              </div>
            </div>
          </div>
          <v-form>
            <v-container>
              <div>รายการที่อยู่</div>
              <button type="button" class="btn btn-submit" >+ เพิ่มที่อยู่</button>
            </v-container>
          </v-form>
          
          </div>
          <div class="tag-bar-heade" style="margin-top:1.5rem">
            <div class="heade-blog">
            <div
              style="
                width: 5px;
                height: 40px;
                border-radius: 1px;
                background-color: rgb(3, 155, 229);
                float: left;
              "
            >
              <div
                style="
                  font-size: 16px;
                  color: rgb(255, 255, 255);
                  width: 50rem;
                  line-height: 40px;
                  float: left;
                  padding-left: 2rem;
                "
              >
                ผู้ติดต่อ
              </div>
            </div>
          </div>
          <v-form>
            <v-container>
              <div>รายชื่อผู้ติดต่อ</div>
              <button type="button" class="btn btn-submit">+ เพิ่มผู้ติดต่อ</button>
            </v-container>
          </v-form>
          
          </div>
        
        </v-col>
        
      </v-row>
    </div>
    </div>
</template>
<style>
.radio-toolbar {
  margin: 10px;
}

.radio-toolbar input[type="radio"] {
  opacity: 0;
  position: fixed;
  width: 0;
}

.radio-toolbar label {
    display: inline-block;
    background-color: #ddd;
    padding: 0rem 1.5rem;
    font-family: sans-serif, Arial;
    font-size: 16px;
    border: 1px solid #444;
    border-radius: 4px;
}

.radio-toolbar label:hover {
  background-color: #dfd;
}

.radio-toolbar input[type="radio"]:checked + label {
    background-image: linear-gradient(#00A4FF, #006BFF);
}
.btn-customer {
  border-radius: 10px;
  margin-left: auto;
  margin-right: auto;
  object-fit: contain;
  z-index: -1;
  box-shadow:none !important;
  border: none;
  background-color: #00A4FF;
  width: 8rem;
  font-weight: 600;
  border-color: #04AA6D;
  color: white;
}
.btn-customer-choose {
  border-radius: 10px;
  margin-left: auto;
  margin-right: auto;
  object-fit: contain;
  z-index: 99999;
  box-shadow:none !important;
  border: none;
  background-color: grey;
  width: 8rem;
  font-weight: 600;
  color: black;
}
.btn-submit {
  display: block;
  border-radius: 10px;
  margin-left: auto;
  margin-right: auto;
  width: 15rem;
  height: 4rem;
  object-fit: contain;
  box-shadow:none !important;
  border: none;
  font-weight: 600;
  border-color: #04AA6D;
  color: green;
  border: 2px dashed black;
}
.v-main__wrap {
  background-color: #dee2e6;
}
.heade-blog {
  padding: 10px 0px;
  border-radius: 6px;
  background-image: linear-gradient(to right, #0575e6 -58%, #021b79 58%);
  box-shadow: 8px 8px 20px 0 rgb(0 0 0 / 8%);
  height: 60px;
}
.tag-bar-heade {
    float: left;
    border-radius: 6px;
    background-color: #ffffff;
    border: solid 0.5px #aeaeae;
    width: 101%;
}
.switch-field label, .switch-field2 label {
    display: inline-block;
    width: 50%;
    background-image: linear-gradient(to bottom, #ffffff, #e7e9ea 83%, #d7dada);
    color: #181a1b;
    font-size: 14px;
    font-weight: normal;
    text-align: center;
    text-shadow: none;
    padding: 6px 14px;
    border: 1px solid #039be5;
}
strong{
  color: #039be5;
}
.transition{
  transition: all .3s ease-out;
}
.heading{
  text-align: center;
  font-size:0.8em;
  
}
</style>
<script>
export default {
  data(){
    return{
      cho:true,
      cho2:false,
    }
  },
  methods: {
        switchCa(){
          this.cho = true;
          this.cho2 = false;
        },
        switchCb(){
          this.cho = false;
          this.cho2 = true;
        },
        showModal() {
        this.$refs['my-modal'].show()
      },
      }
}
</script>
