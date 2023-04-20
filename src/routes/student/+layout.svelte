
<script lang='ts'>
	import { onMount } from 'svelte';
 
	import SideBar from '$lib/sidebar.svelte';
	import SideBarToggle from '$lib/SideBarToggle.svelte';
	import PageHeader from '$lib/PageHeader.svelte';
	let isOpen=false;
	 function handleToggleMenu(){
        //isOpen=!isOpen;
	 }
</script>

<div class="bg-gray-50 dark:bg-slate-900"> 
	<!-- ========== MAIN CONTENT ========== -->
	<div class="drawer  drawer-mobile">
		<input id="my-drawer" type="checkbox" class="drawer-toggle" />
		<div class="drawer-content">
		  <!-- Page content here -->
		  <SideBarToggle on:toggle={handleToggleMenu}  />
		</div> 
		<div class="drawer-side">
		  <label for="my-drawer" class="drawer-overlay"></label>
		   <!-- Add SideBar Component Here-->
			<SideBar {isOpen } />
			<!-- SideBar Component-->
		</div>
          <!-- Content -->
          <div class="w-full pt-10 px-4 sm:px-6 md:px-8 lg:pl-72">
            <PageHeader />
            <slot></slot>
                
            </div>
        <!-- End Content -->
    </div> 
	
  
	<!-- ========== END MAIN CONTENT ========== -->
</div>