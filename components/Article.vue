<template>
  <div>
    <div class="flex-item box">
						<div class="image fit">
							<!-- <img :src='"("+ img +")"' alt="" /> -->
						</div>
						<div class="content">
							<h3>{{title}}</h3>
              <p>{{category}}</p>
							<p>{{resume}}</p>
              <p>{{date}}</p>
              <p>{{urlArticle}}</p>
						</div>
					</div>
  </div>
</template>
<script>
export default {
  name:"Article",
  data(){
    return{

    }
  },
  props: ["title", "urlArticle","date","resume","category"]
}
</script>