<template>
	<footer class="bg-dark text-center text-white">
		<!-- Grid container -->
		<div class="container p-4">
			<!-- Section: Social media -->
			<section class="mb-4">
				<a class="me-3" href="#!" role="button" v-for="(socialMedia, socialMediaIndex) in socialNetworks" :key="socialMediaIndex">
					<b-icon :icon="socialMedia.icon" variant="light" font-scale="2"></b-icon>
				</a>
			</section>
			<!-- Section: Social media -->

			<!-- Section: Form -->
			<section class="">
				<form action="">
					<!--Grid row-->
					<div class="row d-flex justify-content-center">
						<!--Grid column-->
						<div class="col-auto">
							<p class="pt-2">
								<strong>Suscríbete para recibir nuestras noticias</strong>
							</p>
						</div>
						<!--Grid column-->

						<!--Grid column-->
						<div class="col-md-5 col-12">
							<!-- Email input -->
                            <input type="email" id="form5Example21" class="form-control" placeholder="Correo electrónico"/>
						</div>
						<!--Grid column-->

						<!--Grid column-->
						<div class="col-auto">
							<!-- Submit button -->
							<button type="submit" class="btn btn-outline-light mb-4">Suscribir</button>
						</div>
						<!--Grid column-->
					</div>
					<!--Grid row-->
				</form>
			</section>
			<!-- Section: Form -->

			<!-- Section: Text -->
			<section class="mb-4">
				<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt distinctio earum repellat quaerat voluptatibus placeat nam, commodi optio pariatur est quia magnam eum harum corrupti dicta, aliquam sequi voluptate quas.</p>
			</section>
			<!-- Section: Text -->

			<!-- Section: Links -->
			<section class="">
				<!--Grid row-->
				<div class="row">
					<!--Grid column-->
					<div class="col-lg-3 col-md-6 mb-4 mb-md-0" v-for="number in 4" :key="number">
						<h5 class="text-uppercase">Links</h5>

						<ul class="list-unstyled mb-0">
							<li v-for="link in 4" :key="link">
								<a href="#!" class="text-white">Link {{ link }}</a>
							</li>
						</ul>
					</div>
					<!--Grid column-->
				
				</div>
				<!--Grid row-->
			</section>
			<!-- Section: Links -->
		</div>
		<!-- Grid container -->

		<!-- Copyright -->
		<div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2)">
			© 2022 Copyright:
			<a class="text-white" href="#">PeakU.co</a>
		</div>
		<!-- Copyright -->
	</footer>
</template>

<script>
export default {
	name: "CustomFooter",
    data() {
        return {
            socialNetworks: [
                { icon: "facebook", url: "" },
                { icon: "instagram", url: "" },
                { icon: "twitter", url: "" },
                { icon: "linkedin", url: "" },
            ]
        }
    },
};
</script>

<style lang="scss" scoped></style>
