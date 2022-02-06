 <template>
   <div class="col-sm-6 col-lg-4 mb-4" data-aos="fade-up">
        <div v-for="job in jobs" :key="job.id" class="job">
          <router-link :to="{ name: 'Details', params: { id: job.id }}">
            <div class="block-4">
              <figure class="block-4-image">
                <a href="shop-single.html">
                  <img src="https://chromium.themes.zone/toolshop/wp-content/uploads/sites/14/2017/06/prod_3-300x300.jpg" alt="Image placeholder"
                    class="img-fluid"/>
                </a>
              </figure>       
            </div>
            <h2>{{job.title}}</h2> 
            <p class="item-card-rating-wrapper">
              <span class="fa fa-star rating-star-checked"></span>
              <span class="fa fa-star rating-star-checked"></span>
              <span class="fa fa-star rating-star-checked"></span>
              <span class="fa fa-star"></span>
              <span class="fa fa-star"></span>
            </p>
            <p class="font-weight-bold item-card-price">$ 50</p>
          </router-link>
        </div>
         <!-- <p class="item-card-header" >
           
        </p> -->
         
      </div>
</template>



<script>

export default {
  data() {
    return {
      jobs: []
    };
  },
  mounted(){
    fetch('http://localhost:3000/jobs')
    .then((res) => res.json())
    .then(data => this.jobs = data)
    .catch(console.log(err.message))
    
  }
};
</script>
