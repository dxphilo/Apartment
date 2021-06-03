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
        type="tel"
        class="py-2 px-12 outline-none shadow-lg rounded-sm"
        id="phone"
        name="phone"
        placeholder="Enter Tel no"
        pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}"
        v-model="phone"
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
import { upload } from "../backend/routes/fileupload";

const statusInitial = 0,
  statusSaving = 1,
  statusSuccess = 2,
  statusFailed = 3;

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
      currentStatus: null,
      uploadedFiles: [],
      uploadError: null,
      uploadFieldName: "photos",
    };
  },
  computed: {
    isInitial() {
      return this.currentStatus === statusInitial;
    },
    isSaving() {
      return this.currentStatus === statusSaving;
    },
    isSuccess() {
      return this.currentStatus === statusSuccess;
    },
    isFailed() {
      return this.currentStatus === statusFailed;
    },
  },
  methods: {
    // reset the form to initial state
    reset() {
      this.currentStatus = statusInitial;
      this.uploadedFiles = [];
      this.uploadError = null;
    },
    // save theimage to the server
    saveImage(formData) {
      this.currentStatus = statusSaving;
      upload(formData)
        .then((img) => {
          this.uploadedFiles = [].concat(img);
          this.currentStatus = statusSuccess;
        })
        .catch((err) => {
          this.uploadError = err.response;
          this.currentStatus = statusFailed;
        });
    },

    // handle file changes
    fileChange(fieldName, fileList) {
      const formData = new FormData();
      if (!fileList.length) return;
      // append the files to FormData

      Array.from(Array(fileList.length).keys()).map((img) => {
        formData.append(fieldName, fileList[img], fileList[img].name);
      });
      // save the image files data
      this.save(formData);
    },
  },
  mounted() {
    this.reset();
  },
};
</script>
<style scoped>
.postapartment {
  background-image: url("../assets/2.webp");
}
</style>