<script lang="ts">
	import { cn } from "@/utils.js";
	import {Button} from "@/components/ui/button";
	import {FeedbackForm} from "../index";

	let className: string | undefined | null = undefined;
	export { className as class };

	let feedbackOpen = false;
	function openFeedbackForm() {
		feedbackOpen = true;
	}

</script>

<nav class={cn("flex items-center space-x-4 lg:space-x-6", className)}>
	<a href="/" class="hover:text-primary text-sm font-medium transition-colors">
		Dashboard
	</a>
	<FeedbackForm/>
</nav>


