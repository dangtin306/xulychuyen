<template>
    <div class="fixrow row">
        <div v-if="status2 != 1 && status2 != 3" >
      <div class="col mt-0">
      <div  class='mt-4 mx-2 items-center justify-center from-teal-100 via-teal-300 to-teal-500 '>
    
        <div  class='w-full max-w-2xl px-10 py-8 mx-auto bg-white rounded-lg shadow-xl'>
           
            <div class='max-w-xl mx-auto  space-y-3'>
           
                  <div class="col-lg-6">
                      <div class="form-group">
                        <label for="countries2" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-400">Chọn nền tảng</label>
        
                  <select  id="countries2" class="
                  selectpicker sp1 form-control"   @change="onChange()"   name="nhamang" v-model="modeok">
                      <option v-for="option in options" :value="option.value">
                        {{ option.text }}
                      </option>
                    </select>
                    <br>
                    <div  v-if="chondichvu == 2" x-show="showen">
                    <label for="countries" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-400">Chọn dịch vụ</label>
                    <select  id="countries" class="form-control selectpicker sp2"  @change="onChange2()"   name="theloai" v-model="modeok">
                      <option v-for="option in options2" :value="option.value">
                        {{ option.text }}
                      </option>
                    </select>
                </div>

                    <div  v-if="chondichvu == 2" x-show="showen">
                      <label for="dichvu" class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-400">Chọn dịch vụ</label>
                      <select  id="dichvu" class="form-control selectpicker sp3" data-width="auto" data-size="7"  data-live-search="true"  @change="onChange3()"   name="dichvu" v-model="dichvu">
                        <option v-for="option in options3" :value="option.id">
                          {{ option.money }} Xu     {{ option.name }}
                        </option>
                      </select>
                      </div>
                      </div>
                    </div>
                    <div  v-if="chondichvu == 10" x-show="showen">
                    <p>Nhập 1 tên riêng </p>
  <input class="form-control form-control-alternative" v-model="lienketchay" placeholder="Nhập 1 tên riêng" />
  <!-- {{ content }} -->
</div>

                <div  v-if="chondichvu == 1" x-show="showen">
      
              </div>
                  <button  @click="xacnhan"
                  class='flex break-inside bg-purple-400 hover:bg-purple-300 rounded-3xl px-8 py-2 mb-3 w-full dark:bg-slate-800 dark:text-white'>
                  <div class='flex items-center justify-between flex-1'>
                    <div v-if="nutxuly == '1'" class="spinner-border" role="status">
                   
                    </div>
                 
                    <span class='text-lg font-medium text-white '> {{ nutorder }} </span>
                    <svg  width='17' height='17' viewBox='0 0 17 17' fill='none' xmlns='http://www.w3.org/2000/svg'>
                      <path fillRule='evenodd' clipRule='evenodd'
                        d='M0 8.71423C0 8.47852 0.094421 8.25246 0.262491 8.08578C0.430562 7.91911 0.658514 7.82547 0.896201 7.82547H13.9388L8.29808 2.23337C8.12979 2.06648 8.03525 1.84013 8.03525 1.60412C8.03525 1.36811 8.12979 1.14176 8.29808 0.974875C8.46636 0.807989 8.6946 0.714233 8.93259 0.714233C9.17057 0.714233 9.39882 0.807989 9.5671 0.974875L16.7367 8.08499C16.8202 8.16755 16.8864 8.26562 16.9316 8.3736C16.9767 8.48158 17 8.59733 17 8.71423C17 8.83114 16.9767 8.94689 16.9316 9.05487C16.8864 9.16284 16.8202 9.26092 16.7367 9.34348L9.5671 16.4536C9.39882 16.6205 9.17057 16.7142 8.93259 16.7142C8.6946 16.7142 8.46636 16.6205 8.29808 16.4536C8.12979 16.2867 8.03525 16.0604 8.03525 15.8243C8.03525 15.5883 8.12979 15.362 8.29808 15.1951L13.9388 9.603H0.896201C0.658514 9.603 0.430562 9.50936 0.262491 9.34268C0.094421 9.17601 0 8.94995 0 8.71423Z'
                        fill='white' />
                    </svg>
                  </div>
                </button>
               
                  <div
                      class="bg-white border border-slate-300 shadow-lg rounded-md gap-4 p-4  flex-row items-center justify-center">
                      <section class="w-6 flex flex-col items-center justify-start">
                          <svg width="100%" viewBox="0 0 15 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                              <path
                                  d="M7.5 13.25C10.9518 13.25 13.75 10.4518 13.75 7C13.75 3.54822 10.9518 0.75 7.5 0.75C4.04822 0.75 1.25 3.54822 1.25 7C1.25 10.4518 4.04822 13.25 7.5 13.25Z"
                                  stroke="#21ce8f" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" />
                              <path
                                  d="M4.3269 7.96143C4.80767 9.69219 6.73075 10.7499 8.46152 10.2691C9.51921 9.8845 10.3846 9.01912 10.6731 7.96143"
                                  stroke="#21ce8f" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" />
                              <path
                                  d="M10.0481 5.55767C9.91536 5.55767 9.80774 5.45005 9.80774 5.31729C9.80774 5.18453 9.91536 5.0769 10.0481 5.0769"
                                  stroke="#21ce8f" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" />
                              <path
                                  d="M10.0481 5.5577C10.1809 5.5577 10.2885 5.45008 10.2885 5.31732C10.2885 5.18456 10.1809 5.07693 10.0481 5.07693"
                                  stroke="#21ce8f" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" />
                              <path
                                  d="M4.95193 5.55767C4.81917 5.55767 4.71155 5.45005 4.71155 5.31729C4.71155 5.18453 4.81917 5.0769 4.95193 5.0769"
                                  stroke="#21ce8f" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" />
                              <path
                                  d="M4.95197 5.5577C5.08473 5.5577 5.19235 5.45008 5.19235 5.31732C5.19235 5.18456 5.08473 5.07693 4.95197 5.07693"
                                  stroke="#21ce8f" stroke-width="1" stroke-linecap="round" stroke-linejoin="round" />
                          </svg>
                      </section>
                      <section class=" flex flex-col items-start justify-end gap-1">
                          <h1 class="text-base font-semibold text-zinc-800 antialiased">Kết quả : </h1>
                          <div class="users">
                            <div class="loading" v-if="loading">
                                Loading...
                            </div>
                            <div v-if="users">
                            <form id="search">
                                 <input name="query" class="form-control form-control-alternative" placeholder="Search" v-model="searchQuery">
                              </form>
                              <DemoGrid
                                :data="gridData"
                                :columns="gridColumns"
                                :filter-key="searchQuery">
                              </DemoGrid>
                            <div v-if="error" class="error">
                                {{ error }}
                            </div>
                        </div>
                       
                        </div>
                          <p v-if="modeok == 'danhdaumuc8'" class="text-sm font-medium text-zinc-400 antialiased">
<h4 v-html="ketquaok"></h4>
  
                          </p>
                      </section>
                    
                  
              </div>
          </div>
     
          </div>
          <br><br><br><br>
        </div>
      </div>
    
    </div>
   
  
  
    </div>
</template>
<script>
// import helloworld from '!raw-loader!./pg32846.txt' ;
import Swal from 'sweetalert2' ;
import DemoGrid from '../components/Grid2.vue';
import { hamlaychutruoc , hamdemdong ,hamlaychusau2 , chimuctentruyen , laytudongtruoc , laytrongkhoangdong ,demdongbaonhieutu ,hamdemchu , laytudongsau  }  from './hamxulychu.js' ;
    import axios from 'axios' ;
   export default {
   
      data() {
        return {
            gridColumns: ['name', 'power'],
    gridData: [
      { name: 'Chuck Norris', power: Infinity },
      { name: 'Bruce Lee', power: 9000 },
      { name: 'Jackie Chan', power: 7000 },
      { name: 'Jet Li', power: 8000 }
    ] ,
    count : null ,
            loading: null ,
            status2: null ,
            users: null ,
            searchQuery: null,
            error: null ,
            chondichvu: null ,
            ketquaok : null ,
            lienketchay: null ,
            ádkjbasdjk: null ,
            content:null,
            chondichvu2:null ,
        fileContent: '' ,
        ashdbhabsdk: null ,
        modeok: null ,
        jsonArr2: null ,
        chimuccauthoai: null ,
        asdasdsadasdas: null ,
        helloworld: null ,
        ashdhjsahdb: null ,
        chimucchuyen: null ,
        nutxuly: null ,
        nutorder: 'Xác nhận',
        tencaccauchuyen: [
        { text: 'THE TWO DROVERS', value: '1' } , 
        { text: 'MR. DEUCEACE', value: '2' } ,
        { text: `THE BROTHERS`, value: '3' }  ,
        { text: `"DR. MANETTE'S MANUSCRIPT"` , value: '4' }  ,
        { text: `THE CALDRON OF OIL` , value: '5' }  ,
        { text: `THE BURIAL OF THE TITHE` , value: '6' }  ,
        { text: `THE KNIGHTSBRIDGE MYSTERY` , value: '7' }  ,
        { text: `THE COURTING OF DINAH SHADD` , value: '8' }  ,
        { text: `THE SIRE DE MALETROIT'S DOOR` , value: '9' }  ,
        { text: `THE SECRET OF GORESTHORPE GRANGE` , value: '10' }  ,
        { text: `A CHANGE OF TREATMENT` , value: '11' }  ,
        { text: `THE STICKIT MINISTER` , value: '12' }  ,
        { text: `THE LAMMAS PREACHING` , value: '13' }  ,
        { text: `AN UNDERGRADUATE'S AUNT` , value: '14' }  ,
        { text: `THE SILHOUETTES` , value: '15' }  ,
        { text: `MY BROTHER HENRY` , value: '16' }  ,
        { text: `GILRAY'S FLOWER-POT` , value: '17' }  ,
        { text: `MR. O'LEARY'S SECOND LOVE` , value: '18' }  ,
        { text: `THE INDIFFERENCE OF THE MILLER OF HOFBAU` , value: '19' }  ,
        { text: `THE STOLEN BODY` , value: '20' }  ,
        { text: `THE LAZARETTE OF THE "HUNTRESS"` , value: '21' }  ,
        { text: `THE GREAT TRIANGULAR DUEL` , value: '22' }  ,
        { text: `THREE THIMBLES AND A PEA` , value: '23' }  ,
      ],
        options: [
        { text: 'Chọn 1 nền tảng', value: '' } , 
        { text: 'Thống kê tên riêng', value: 'đanhdaumuc1' } ,
        { text: 'Đánh chỉ mục theo tên riêng của chuyện', value: 'đanhdaumuc2' }  ,
        { text: 'Đánh dấu chỉ mục theo thứ tự dòng ', value: 'đanhdaumuc3' }  ,
        { text: 'Đánh chỉ mục chương của chuyện ', value: 'đanhdaumuc4' }  ,
        { text: 'Tra cứu chỉ mục theo nội dung chuyện ', value: 'danhdaumuc7' }  ,
        { text: 'Tra cứu chỉ mục tên riêng ', value: 'danhdaumuc8' }  ,
        { text: 'Chỉ mục một số câu thoại ngắn', value: 'danhdaumuc9' }  
      ],
      options2:  [
        { text: 'Chọn 1 nền tảng', value: '' } , 
        { text: 'Thống kê tên riêng', value: 'đanhdaumuc1' } ,
        { text: 'Đánh dấu chỉ mục theo thứ tự dòng', value: 'đanhdaumuc2' }  ,
        { text: 'Đánh chỉ mục riêng của chuyện ', value: 'đanhdaumuc3' }  ,
      ],
      options3: null ,
        }
      },
      components: {
    DemoGrid
  },
      created(){

                $('.selectpicker').selectpicker('refresh');
                setTimeout(() => {    
                    $('.selectpicker').selectpicker('refresh');
                    setTimeout(() => {     
         $('.sp1').selectpicker('toggle');  }, 300)
                }, 300) ;
                this.getfiletext() ;
     
      },
      methods: {
        onChange()
        {
            this.users = null ,
            this.ketquaok = null ,
            this.gridData = null
            if ( this.modeok == 'danhdaumuc8'    )
        {

         this.chondichvu =     10 ;


        }
        else
        {
            this.chondichvu =     null ;
        }
        } ,
        getfiletext()
        {

            axios
                .get('https://hust.media/img/truyen.php')
                .then(response => {
                       
              this.helloworld = response.data  ;
            //   console.log(this.helloworld);
            
                });
        },xacnhan(){
            this.nutxuly = 1 ;
            this.nutorder = 'chờ xíu nhé' ;
        console.log(this.modeok);
        if (this.modeok == 'thongketenrieng'  )
        {
          var asdsadasd = this.helloworld ;
          var fdgdfgdfgfd = this.lienketchay ;
          this.demthongke(asdsadasd , fdgdfgdfgfd) 
          this.nutxuly = 0 ;
            this.nutorder = '=)) tiếp tục thôi nào' ;
        // console.log(this.lienketchay);
        }
        else  if ( this.modeok == 'đanhdaumuc1'    )
        {
            setTimeout(function () { 
      
      this.nutxuly = 0 ;
      this.đanhdaumuc1ok() ;
 
      this.users = 1 ;
                 this.nutorder = '=)) tiếp tục thôi nào' ;
           }.bind(this), 1000);
        }
      else  if ( this.modeok == 'đanhdaumuc2'    )
        {
            setTimeout(function () { 
      
                this.đanhdaumuc2ok() ;
           }.bind(this), 500);

        setTimeout(function () { 
      
      this.nutxuly = 0 ;
      this.users = 1 ;
                 this.nutorder = '=)) tiếp tục thôi nào' ;
           }.bind(this), 14000 );
        }
        else  if ( this.modeok == 'đanhdaumuc3'    )
        {
         this.danhchimuc() ;
            setTimeout(function () { 
      
      console.log(this.jsonArr2)  ;
      this.nutxuly = 0 ;
      this.gridColumns= ['stt', 'tentruyen' , 'batdau' , 'ketthuc'    ],
      this.gridData = this.jsonArr2 ,
      this.users = 1 ;
                 this.nutorder = '=)) tiếp tục thôi nào' ;
           }.bind(this), 1000);
        }
        else  if ( this.modeok == 'đanhdaumuc4'    )
        {
          this.đanhdaumuc4() ;
          console.log(this.chimucchuyen);
          setTimeout(function () { 
      this.nutxuly = 0 ;
      this.gridColumns= ['stt', 'tentruyen' , 'chuong' , 'doanchuong'   ],
      this.gridData = this.chimucchuyen ,
      this.users = 1 ;
                 this.nutorder = '=)) tiếp tục thôi nào' ;
           }.bind(this), 1000);
           
        }
        else  if ( this.modeok == 'đanhdaumuc5'    )
        {

          var ashdbhbsajdjknaskd =     laytudongtruoc(this.lienketchay , this.helloworld) ;
         console.log(ashdbhbsajdjknaskd);
         this.nutxuly = 0 ;
            this.nutorder = '=)) tiếp tục thôi nào' ;

        }
        else  if ( this.modeok == 'danhdaumuc7'    )
        {

            this.đanhdaumuc4() ;
            setTimeout(function () { 
      
      this.nutxuly = 0 ;
      this.gridColumns= ['stt', 'tentruyen' , 'doanchuyen'   ],
      this.gridData = this.chimucchuyen ,
      this.users = 1 ;
                 this.nutorder = '=)) tiếp tục thôi nào' ;
           }.bind(this), 1000);
    }
        else  if ( this.modeok == 'danhdaumuc8'    )
        {

            var asdsadasd = this.helloworld ;
          var fdgdfgdfgfd = this.lienketchay ;
        this.danhdaumuc8ok(fdgdfgdfgfd,asdsadasd) ;
    }
        else  if ( this.modeok == 'danhdaumuc9'    )
        {
          this.đanhdaumuc4() ;
       var keyCount  = Object.keys(this.chimucchuyen).length ;

       this.chimuccauthoai = [] ;
for (let okok = 0; okok < keyCount; okok++)

    setTimeout(function () { 
      console.log(okok)  ;
 this.demdongbaonhieutu(okok) ;
  
 }.bind(this), 350 * okok);


 setTimeout(function () { 
      
 console.log(this.chimuccauthoai)  ;
 this.nutxuly = 0 ;
 this.gridColumns= ['stt', 'tentruyen' , 'batdau','ketthuc'  ,'cauthoaitieubieu' ],
 this.gridData = this.chimuccauthoai ,
 this.users = 1 ;
            this.nutorder = '=)) tiếp tục thôi nào' ;
      }.bind(this), 9000);
    
        }
          },
          danhchimuc(){
            var keyCount  = Object.keys(this.tencaccauchuyen).length ;

var jsonArr = [];
for (let i = 0; i < keyCount ; i++) {
      // var obj = JSON.stringify(jsonObject);
      let   sdsdfsdfsdf = this.tencaccauchuyen[i].text ;
                var ashdbhbsajdjknaskd =  chimuctentruyen(sdsdfsdfsdf , this.helloworld ) ;
                let asdjasd = i + 1 ;
 jsonArr.push({
        stt: asdjasd ,
        tentruyen: sdsdfsdfsdf ,
        batdau: ashdbhbsajdjknaskd
    });
}
var keyCount  = Object.keys(jsonArr).length ;
this.jsonArr2 = [];
for (let i = 0; i < keyCount ; i++) {
 let asdasasd = i + 1 ;
  let   stt = jsonArr[i].stt ;
  let   tentruyen = jsonArr[i].tentruyen ;
  let   batdau = jsonArr[i].batdau ;
  if ( stt != 23 )
  {
    let   ketthuc = jsonArr[asdasasd].batdau - 1 ;
    this.jsonArr2.push({
        stt: stt ,
        tentruyen: tentruyen ,
        batdau: batdau ,
        ketthuc: ketthuc
    });
  }
  else
  {
    let   ketthuc = 13740 ;
    this.jsonArr2.push({
        stt: stt ,
        tentruyen: tentruyen ,
        batdau: batdau ,
        ketthuc: ketthuc
    });
  }


}


  
          },
          async asdasdasd(okok)
          {
   

     await  this.demdongbaonhieutu(okok) ;
 

          },
          danhdaumuc8ok(fdgdfgdfgfd,asdsadasd)
          {
            this.timdongchu(fdgdfgdfgfd , asdsadasd) 
          this.danhchimuc() ;
      var keyCount  = Object.keys(this.jsonArr2).length ;
      for (let i = 0; i < keyCount ; i++) {
        let   batdau = this.jsonArr2[i].batdau ;
        let   ketthuc = this.jsonArr2[i].ketthuc ;
        let   tentruyen = this.jsonArr2[i].tentruyen ;
if ( this.count < batdau )
{

}
else if ( this.count > batdau && this.count < ketthuc )
{
    this.asdasdsadasdas = tentruyen ;
     this.ashdhjsahdb = this.count - batdau + 1 ;
    this.ketquaok = 'Tên truyện: ' + tentruyen + `<br>` + 'Xuất hiện ở dòng : '+ this.count
    +  `<br>` + 'Xuất hiện ở dòng trong truyện: '+ this.ashdhjsahdb  ;
}
          this.nutxuly = 0 ;
            this.nutorder = '=)) tiếp tục thôi nào' ;

        }
          },
          demdongbaonhieutu(okok){
            let   stt = this.chimucchuyen[okok].stt ;
  let   tentruyen = this.chimucchuyen[okok].tentruyen ;
  let   batdau = this.chimucchuyen[okok].batdau ;
  let   ketthuc = this.chimucchuyen[okok].ketthuc ;
  let   chuong = this.chimucchuyen[okok].chuong ;
  let   doanchuyen = this.chimucchuyen[okok].doanchuyen ;
  let toanbo = doanchuyen ;
            let sadsadsda = '' ;
  for (let i = 0; i < 100 ; i++) {
    
  var sadasdasd  = encodeURI(toanbo) ;
  var chulay  = '%0D%0A' ;

  const first6 = sadasdasd.slice(0, 6);
  const first12 = sadasdasd.slice(0, 12);
  // console.log(first6);
if (first6 == '%0D%0A' || first6 == '' || first12 == '%0D%0A%0D%0A' )
{
  // console.log(first6);
  sadasdasd = laytudongsau(chulay,sadasdasd) ;
  sadasdasd = hamlaychutruoc(chulay,sadasdasd) ;
  toanbo = laytudongsau(1,toanbo) ;
  // console.log(sadasdasd);
}
else
{
  let lastFive = '%0D%0A%0D%0A' ;
  var okluon =  hamlaychutruoc(lastFive,sadasdasd) ;

  var okluon3 = decodeURI(okluon) ;
  // console.log(okluon3);
  var okluon2 = hamdemchu (okluon3) ;
  // console.log(okluon2);
 if ( okluon2 < 100 )
 {
  toanbo = laytudongsau(1,toanbo) ;
 }
 else
 {

  for (let y = 80; y < 200 ; y++) {
    const y20 = y + 20 ;
    const first20 = okluon3.slice(y, y20);
     sadsadsda = hamlaychutruoc(first20,okluon3) ;
    var sdfdsfsdffds = hamdemchu (sadsadsda) ;
    // console.log(sdfdsfsdffds);
    var lastChar = sadsadsda.slice(-1); // => "1"
    
 
      if ( sdfdsfsdffds > 70 )
      {
        i = 100 ;
        y = 200 ;
        let cauthoaitieubieu =    sadsadsda ; 
        console.log(cauthoaitieubieu);
    
this.chimuccauthoai.push({
        stt: stt ,
        tentruyen: tentruyen ,
        batdau: batdau ,
        ketthuc: ketthuc ,
        chuong: chuong ,
        doanchuyen: doanchuyen ,
        cauthoaitieubieu: cauthoaitieubieu
    });
      }
      else
      {
  
      }
 

  }
  i = 100 ;
 


 }

}

   
  }
          },
          đanhdaumuc1ok()
          {
            this.gridColumns= [ 'stt' , 'name' , 'tenrieng' ],
      this.gridData = [
      { stt: 1 , name: 'THE TWO DROVERS', tenrieng: `Donne Fair|England|English|The Highlanders|Robin Oig|God|Hugh Morrison's|Dumfriesshire|Harry Wakefield|Sraithfield|Liddesdale|Cumberland` },
      { stt: 2 , name: 'MR. DEUCEACE', tenrieng: `The Waste|Scot|Mr. Ireby|Sawney|John Fleecebumpkin|Shame|Harkye|Carlisle|Pump Court|Bon Street|Pickledilly|MR. RICHARD BLEWITT|Mr. Dawkins|Oxford|Squire Blewitt` },
      { stt: 3 , name: 'THE BROTHERS', tenrieng: `Gertrude|Trevylyan|Leoline|Warbeck|Rhine|St. Bertrand` },
      { stt: 4 , name: `"DR. MANETTE'S MANUSCRIPT"`, tenrieng: `Alexandre Manette|Beauvais|Paris|December|Doctor Manette` },
      { stt: 5 , name: 'THE CALDRON OF OIL', tenrieng: `WILKIE COLLINS|French|Toulouse|Croix-Daurade|England|Eighteenth Hussars` },
      { stt: 6 , name: 'THE BURIAL OF THE TITHE', tenrieng: `SAMUEL LOVER|Shakespeare|Shakespeare|Phil Mulligan|Biddy|Divil's Biddy|Mr. Coogan|Mr. Coogan|Irishman's|Hoppy Houligan` },
      { stt: 7 , name: 'THE KNIGHTSBRIDGE MYSTERY', tenrieng: `CHARLES READE|Mr. Gardiner|The Captain|Captain Cowen|Daniel Cox` },
      { stt: 8 , name: 'THE COURTING OF DINAH SHADD', tenrieng: `RUDYARD KIPLING|Privates Mulvaney|Ortheris|Learoyd|Shakespeare|Silver's Theater` },
      { stt: 9 , name: `"THE SIRE DE MALETROIT'S DOOR"`, tenrieng: `R. L. STEVENSON|Beaulieu|England|Chateau Landon|Denis` },
      { stt: 10 , name: 'THE SECRET OF GORESTHORPE GRANGE', tenrieng: `SIR ARTHUR CONAN DOYLE|Goresthorpe Grange|Mrs. D'Odd|Matilda` },
    ] 
          },
          đanhdaumuc2ok()
          {  this.đanhdaumuc1ok() ;
            this.ádkjbasdjk = this.gridData ;
             var keyCount  = Object.keys(this.ádkjbasdjk).length ;
             this.gridData = [];
      for (let i = 0; i < keyCount ; i++) {
        let   stt = this.ádkjbasdjk[i].stt ;
        let   name = this.ádkjbasdjk[i].name ;
        let   tenrieng = this.ádkjbasdjk[i].tenrieng ;
this.demthongke('|',tenrieng) ;
       let hasbdkjaskjd = this.count ;  
       let dbshbchsdbh = null ;
      
      for (let y = 0; y < hasbdkjaskjd ; y++) {
         dbshbchsdbh =     hamlaychutruoc('|',tenrieng) ;
        console.log(dbshbchsdbh) ;
        tenrieng =     hamlaychusau2('|',tenrieng) ;
        this.danhdaumuc8ok(dbshbchsdbh,this.helloworld) ;
        this.ashdhjsahdb ;
        this.gridColumns = ['tenrieng', 'tentruyen' , 'xuathien'],
        this.gridData.push({
                  tenrieng: dbshbchsdbh ,
        tentruyen: this.asdasdsadasdas ,
        xuathien: 'Xuất hiện ở dòng ' + this.ashdhjsahdb 
    });
      }
 
      console.log(dbshbchsdbh );
        }},
          đanhdaumuc4()
        {
          this.danhchimuc() ;
          var keyCount  = Object.keys(this.jsonArr2).length ;

 this.chimucchuyen = [];
for (let i = 0; i < keyCount ; i++) {
  let   stt = this.jsonArr2[i].stt ;
  let   tentruyen = this.jsonArr2[i].tentruyen ;
  let   batdau = this.jsonArr2[i].batdau ;
  let   ketthuc = this.jsonArr2[i].ketthuc ;
  var ashdbhbsajdjknaskd =    laytrongkhoangdong(batdau,ketthuc, this.helloworld) ;
const substring = "CHAPTER" ;
let cochuongkhong = ashdbhbsajdjknaskd.includes(substring); // true
                // let asdjasd = i + 1 ;

                if ( cochuongkhong ==  true  )
                {
                  if ( stt == 1 )
                  this.chimucchuyen.push({
                  stt: stt ,
        tentruyen: tentruyen ,
        batdau: batdau ,
        ketthuc: ketthuc ,
        doanchuyen: ashdbhbsajdjknaskd ,
        chuong: cochuongkhong ,
        sochuong: 2 ,
        doanchuong: [{ Chuong:1 , batdau: 140 , ketthuc: 426 },{ Chuong:2 , batdau: 427 , ketthuc: 1234 } ]
    });
    else if ( stt == 7 )
    {
      this.chimucchuyen.push({
                  stt: stt ,
        tentruyen: tentruyen ,
        batdau: batdau ,
        ketthuc: ketthuc ,
        doanchuyen: ashdbhbsajdjknaskd ,
        chuong: cochuongkhong ,
        sochuong: 4 ,
        doanchuong: [{ Chuong:1 , batdau: 5227 , ketthuc: 5753 },{ Chuong:2 , batdau: 5754 , ketthuc: 6109 },{ Chuong:3 , batdau: 6110 , ketthuc: 6611 },{ Chuong:4 , batdau: 6611 , ketthuc: 6951 }  ] });
    }
                }
                else
                {
                  this.chimucchuyen.push({
                  stt: stt ,
        tentruyen: tentruyen ,
        batdau: batdau ,
        ketthuc: ketthuc ,
        doanchuyen: ashdbhbsajdjknaskd ,
        chuong: cochuongkhong
    });
                }
               
}

        

          },
        demthongke(chulay , toanbo ) { 
this.count = toanbo.split(chulay).length - 1;
console.log(this.count ); //should output '2'

    },
    timdongchu(chulay , toanbo ) { 
            toanbo =   hamlaychutruoc(chulay,toanbo) ;
            toanbo = encodeURI(toanbo) ;
            this.count = toanbo.split('%0D%0A').length ;

console.log(this.count); //should output '2'

    },

  }
      }
</script>