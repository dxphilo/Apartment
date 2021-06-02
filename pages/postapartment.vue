<template>
  <div
    class="postapartment h-full w-full bg-cover bg-no-repeat bg-center max-h-full object-center pt-10"
  >
    <h1 class="text-center text-4xl py-6">Register Housing</h1>
    <form
      action=""
      class="text-center text-black py-6 tracking-wide leading-7"
      @submit.prevent="postDetails"
      enctype="multipart/form-data"
    >
      <label for="Name" class="text-xl">Name:</label> <br />
      <input
        type="text"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        placeholder="Enter name"
        v-model="name"
      />
      <br />

      <label for="Name" class="text-xl">Email:</label> <br />
      <input
        type="enail"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        placeholder="Enter email"
        v-model="email"
      />
      <br />
      <label for="Name" class="text-xl">Telephone No:</label> <br />
      <input
        type="number"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        placeholder="Enter number"
        v-model="telno"
      />
      <br />

      <label for="Name" class="text-xl">ID No:</label> <br />
      <input
        type="number"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        placeholder="Enter ID NO"
        v-model="idno"
      />
      <br />

      <label for="Name" class="text-xl">Price:</label> <br />
      <input
        type="text"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        placeholder="Enter price range"
        v-model="price"
      />
      <br />
      <span class="text-gray-900">i.e 4,500 - 10,000</span>
      <br />

      <label for="Name" class="text-xl">Size:</label> <br />
      <input
        type="no"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        placeholder="Enter size"
        v-model="size"
      />
      <br />

      <label for="Name" class="text-xl">Location:</label> <br />
      <input
        type="message"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        placeholder="Enter location"
        v-model="location"
      />
      <br />

      <label for="Name" class="text-xl">Images/Photos:</label> <br />
      <input
        type="file"
        multiple
        accept="image/*"
        class="py-1 px-2 bg-white outline-none shadow-lg rounded-sm"
        placeholder="choose images"
      />
      <br />
      <span class="text-gray-900">Upload upto 4 images</span>
      <br />
      <button
        type="submit"
        class="py-1 border-2 border-gray-500 mt-3 px-32 bg-green-500 outline-none focus:outline-none shadow-lg rounded-sm hover:bg-green-600"
      >
        Submit
      </button>
    </form>
  </div>
</template>
 <script>
export default {
  data() {
    return {
      name: "",
      idno: "",
      email: "",
      phone: "",
      location: "",
      price: "",
      size: "",
      images: "",
    };
  },
  methods: {
    postDetails() {},
  },
};
</script>
<style scoped>
.postapartment {
  background-image: url("../assets/2.jpg");
}
</style>