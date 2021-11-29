<template>
    <div>

      <v-container>
        <div class="text1">
          <span>
            สำหรับเข้าสู่ระบบของ<span class="text-style-1"> ตัวท่านเอง</span>
          </span>
        </div>
        <div>

        </div>
        <div class="row login-bg">
          <div class="col-6 btn-login-col" >
            <button type="button" @click="switchA()" class="btn btn-submit btn-login-left">
            Login
            </button>
          </div>
          <div class="col-6 btn-login-col">
            <button type="button" @click="switchB()" class="btn btn-submit btn-login-right">
              Register
            </button>
          </div>
        </div>
        
        <div>
          <template v-if="typeA == true">
            <div class="container v-application--is-ltr v-application">
              <div class="row">
                <div class="col-12">
                  <v-text-field
                    class="animation"
                    label="ชื่อผู้ใช้หรือหมายเลขโทรศัพท์มือถือ"
                    hint="ตัวอักษรต้องมากกว่า 8 ตัว"
                    :rules="rules"
                    hide-details="auto"
                    ><template slot="label"
                      ><span
                        class="icon-USER iconic1"
                        style="padding-right: 5px ; width:261px;"
                      ></span
                      >ชื่อผู้ใช้หรือหมายเลขโทรศัพท์มือถือ</template
                    ></v-text-field
                  >
                </div>
  
                <div class="col-12">
                  <v-text-field
                    :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
                    :rules="[rules.required, rules.min]"
                    :type="show2 ? 'text' : 'password'"
                    name="input-10-2"
                    label="รหัสผ่าน"
                    value=""
                    style="margin-bottom: -15px"
                    class="input-group--focused animation"
                    @click:append="show2 = !show2"
                    ><template slot="label"
                      ><span
                        class="icon-Password iconic1"
                        style="padding-right: 5px"
                      ></span
                      >รหัสผ่าน</template
                    ></v-text-field
                  >
                </div>
                <div data-app class="text-center bbbbbbbbbbb">
                  <v-bottom-sheet class="aaaaaaaaaaaaaaaaaaaaa" v-model="sheet">
                    <template v-slot:activator="{ on, attrs }">
                      <a v-bind="attrs" v-on="on">ลืมรหัส</a>
                    </template>
                    <v-sheet class="text-center" height="100vh">
                      <div class="row m-0">
                        <div class="col-12" style="text-align: right">
                          <i class="fas fa-times" @click="sheet = !sheet"></i>
                        </div>
                      </div>
                      <div class="row m-0">
                        <div class="col-12">

                          <div>
                            <h1 style="padding-top:16px;">ผู้ใช้ลืมรหัสผ่าน</h1>
                            <div class="cut-text">
                              <div style="padding-top:15px;">กรุณากรอกเบอร์โทรศัพท์เพื่อทำการยืนยันตัวตน</div>
                              <div>ซึ่งจะส่ง SMS รหัส OTP ไปยังเบอร์ที่ท่านกรอกไว้</div>
                              <div>สำหรับการสร้างรหัสผ่านใหม่</div>
                            </div>
                            <div>
                              <div class="col-4" style="width:261px; margin:auto;">
                                <v-text-field
                                  autocomplete="false"
                                  placeholder="กรุณากรอกเบอร์โทรศัพท์"
                                  style="width:261px; "
                                  >
                                  ></v-text-field
                                >
                              </div>
                            </div>
                          </div>
                        </div>
                      </div>
                    </v-sheet>
                  </v-bottom-sheet>
                </div>
              </div>
            </div>
          </template>
          <template v-else-if="typeB == true">
            <div class="container v-application--is-ltr v-application">
              <div class="row">
                <div class="col-6">
                  <v-select
                    label="รหัสร้าน"
                    class="animation-member"
                    :items="items2"
                    ><template slot="label">
                      <span
                        class="icon-code_shop iconic1"
                        style="padding-right: 5px"
                      ></span>
                      รหัสร้าน<a class="req">*</a></template
                    ></v-select
                  >
                </div>
                <div class="col-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อร้าน"
                    :rules="rules"
                    hide-details="auto"
                    ><template slot="label">
                      <span
                        class="icon-Store iconic1"
                        style="padding-right: 5px"
                      ></span>
                      ชื่อร้าน <a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-6">
                  <v-text-field
                    class="animation-member"
                    label="ชื่อที่เรียกลูกค้า"
                    :rules="rules"
                    hide-details="auto"
                    ><template slot="label">
                      <span
                        class="icon-USER iconic1"
                        style="padding-right: 5px"
                      ></span>
                      ชื่อที่เรียกลูกค้า<a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-6">
                  <v-text-field
                    class="animation-member"
                    label="มือถือลูกค้า"
                    :rules="rules"
                    hide-details="auto"
                    ><template slot="label">
                      <span
                        class="icon-Phone iconic1"
                        style="padding-right: 5px"
                      ></span>
                      มือถือลูกค้า<a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-6">
                  <v-select
                    label="ตำแหน่ง"
                    class="animation-member"
                    :items="items2"
                    ><template slot="label">
                      <span
                        class="icon-Occupation iconic1"
                        style="padding-right: 5px"
                      ></span>
                      ตำแหน่ง<a class="req">*</a></template
                    ></v-select
                  >
                </div>
                <div class="col-6">
                  <v-text-field
                    class="animation-member"
                    label="จังหวัด"
                    :rules="rules"
                    hide-details="auto"
                    ><template slot="label">
                      <span
                        class="icon-Pin iconic1"
                        style="padding-right: 5px"
                      ></span>
                      จังหวัด<a class="req">*</a></template
                    ></v-text-field
                  >
                </div>
                <div class="col-6">
                  <v-select
                    label="อำนาจสั่งซื้อ"
                    class="animation-member"
                    :items="items2"
                  >
                    <template slot="label">
                      <span
                        class="icon-Decide iconic1"
                        style="padding-right: 5px"
                      ></span>
                      อำนาจสั่งซื้อ<a class="req">*</a></template
                    ></v-select
                  >
                </div>
                <div class="col-6">
                  <v-text-field
                    class="animation-member"
                    label="หมายเหตุ"
                    :rules="rules"
                    hide-details="auto"
                    ><template slot="label">
                      <span
                        class="icon-NOTE iconic1"
                        style="padding-right: 5px"
                      ></span>
                      หมายเหตุ</template
                    ></v-text-field
                  >
                </div>
              </div>
            </div>
          </template>
        </div>
        <div v-if="typeA == true" style="padding-top: 60px">
          <button type="button" class="btn btn-submit">ลงชื่อเข้าใช้</button>
        </div>
        <div v-if="typeB == true" style="padding-top: 20px">
          <button type="button" @click="check()" class="btn btn-submit">
            ยืนยันการลงทะเบียน
          </button>
        </div>
      </v-container>
    </div>
</template>
<style>
  .login-bg{
      height: 55px;
      background-color: #e8f3fe;
      margin-right: 10px;
      margin-left: 10px;
      margin-top: 15px;
      margin-bottom: 15px;
      border-radius: 15px;
  }
  .btn-login-left{
      background-color: #1e4686;
      width: 100%;
      height: 55px;
      border-radius: 15px;
  }
  .btn-login-right{
        background-color: #e8f3fe;
        width: 100%;
        height: 55px;
        border-radius: 15px;
    }
  .btn-login-col{
    padding-right: 0px;
    padding-left: 0px;
    padding-top: 0px;
  }
</style>
<script>
  export default {
    data: () => ({
      typeA: true,
      typeB: false,
      show2: true,
      password: 'Password',
      tel: '',
      sheet: false,
      email: 'ham@gmail.com',
      rules: [
        (value) => !!value || 'Required.',
        (value) => (value && value.length >= 3) || 'Min 3 characters',
      ],
      items2: ['Foo', 'Bar', 'Fizz', 'Buzz'],
    }),
    methods: {
      switchB() {
        this.typeA = false
        this.typeB = true
      },
      switchA() {
        this.typeA = true
        this.typeB = false
      },
    },
  }
  </script>