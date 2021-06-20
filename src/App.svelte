<script>
	import { onMount } from 'svelte';
	import EditorJS from '@editorjs/editorjs';
	import Header from '@editorjs/header';
	import Underline from '@editorjs/underline';
	import NestedList from '@editorjs/nested-list';
	import Quote from '@editorjs/quote';
	import InlineCode from '@editorjs/inline-code';
	import CodeTool from '@editorjs/code';
	import Embed from '@editorjs/embed';
	import Marker from '@editorjs/marker';
	// import SimpleImage from '@editorjs/simple-image';
	import ImageTool from '@editorjs/image';
	import Table from'@editorjs/table';

	let editor;

	onMount(() => {
		editor = new EditorJS({
			holder : 'editorjs',
			tools: {
				underline: Underline,
				header: {
					class: Header,
					inlineToolbar: true,
					config: {
						levels: [1, 2, 3, 4],
						defaultLevel: 3
					}
				},
				list: {
					class: NestedList,
					inlineToolbar: true,
					defaultListStyle: 'unordered'
				},
				table: Table,
				quote: Quote,
				inlineCode: InlineCode,
				code: CodeTool,
				embed: Embed,
				marker: Marker,
				image: ImageTool
			},
			data: {
				"time" : 1621485687813,
				"blocks" : [
					{
						"type" : "paragraph",
						"data" : {
							"text" : "Hey. Meet the new Editor. On this page you can see it in action — try to edit this text."
						}
					}
				],
				"version" : "2.20.2"
			},
		});
	});
</script>

<div class="container">
	<div id="editorjs"></div>
</div>

<style>
	:global(body) {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 50px;
		box-sizing: border-box;
		background-color: rgb(218, 240, 240);
	}

	.container {
		min-height: 450px;
		padding: 70px 50px;
		width: 850px;
		background-color: white;
		border-radius: 26px;
	}
</style>