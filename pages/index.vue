<script setup>
useHead({
  title: "Catering dla sportowców!",
});
const obj = ref(null);
const title = ref("");
const props = defineProps({
  itemsMenu: {
    type: Array,
    default: () => [],
    // required: true
  },
});
async function logData() {
  const response = await fetch("https://jsonplaceholder.typicode.com/todos/1");
  obj.value = await response.json();
  title.value = obj.value ? " - " + obj.value.title : "";
  console.log(obj.value.title);
}
onMounted(() => {
  console.log(props.itemsMenu);

  logData();
});
</script>
<template>
  <!-- Page Header Start -->
  <div class="page-header mb-0">
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h2>Doskonały catering!</h2>
        </div>
        <div class="col-12">
          <h3 class="second-header">Doskonałe jedzenie</h3>
        </div>
      </div>
    </div>
  </div>
  <!-- Page Header End -->

  <!-- Food Start -->
  <div class="food mt-0">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-md-4">
          <div class="food-item">
            <i class="flaticon-burger"></i>
            <h2>Śniadania!</h2>
            <p>
              Lorem ipsum dolor sit amet elit. Phasel nec pretium mi. Curabit
              facilis ornare velit non vulputa. Aliquam metus tortor auctor quis
              sem.
            </p>
            <a href="">View Menu</a>
          </div>
        </div>
        <div class="col-md-4">
          <div class="food-item">
            <i class="flaticon-snack"></i>
            <h2>Obiady!</h2>
            <p>
              Lorem ipsum dolor sit amet elit. Phasel nec pretium mi. Curabit
              facilis ornare velit non vulputa. Aliquam metus tortor auctor quis
              sem.
            </p>
            <a href="">View Menu</a>
          </div>
        </div>
        <div class="col-md-4">
          <div class="food-item">
            <i class="flaticon-cocktail"></i>
            <h2>Kolacje!</h2>
            <p>
              Lorem ipsum dolor sit amet elit. Phasel nec pretium mi. Curabit
              facilis ornare velit non vulputa. Aliquam metus tortor auctor quis
              sem.
            </p>
            <a href="">View Menu</a>
          </div>
        </div>
      </div>
    </div>
    <a href="index.html" class="navbar-brand"
      >Test <span>ładownie z serwera{{ title }}</span></a
    >
  </div>
  <!-- Food End -->

  <!-- About Start -->
  <div class="about">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6">
          <div class="about-content">
            <div class="section-header">
              <p>About Us</p>
              <h2>Gotujemy z pasją!</h2>
            </div>
            <div class="about-text">
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Phasellus nec pretium mi. Curabitur facilisis ornare velit non
                vulputate. Aliquam metus tortor, auctor id gravida condimentum,
                viverra quis sem.
              </p>
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Phasellus nec pretium mi. Curabitur facilisis ornare velit non
                vulputate. Aliquam metus tortor, auctor id gravida condimentum,
                viverra quis sem. Curabitur non nisl nec nisi scelerisque
                maximus. Aenean consectetur convallis porttitor. Aliquam
                interdum at lacus non blandit.
              </p>
              <a class="btn custom-btn" href="">Book A Table</a>
            </div>
          </div>
        </div>
        <div class="col-lg-6">
          <div class="about-img">
            <img src="img/team-2.jpg" alt="Image" />
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- About End -->

  <!-- Video Modal Start-->
  <div
    class="modal fade"
    id="videoModal"
    tabindex="-1"
    role="dialog"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog" role="document">
      <div class="modal-content">
        <div class="modal-body">
          <button
            type="button"
            class="close"
            data-dismiss="modal"
            aria-label="Close"
          >
            <span aria-hidden="true">&times;</span>
          </button>
          <!-- 16:9 aspect ratio -->
          <div class="embed-responsive embed-responsive-16by9">
            <iframe
              class="embed-responsive-item"
              src=""
              id="video"
              allowscriptaccess="always"
              allow="autoplay"
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- Video Modal End -->
</template>
<style scoped></style>
