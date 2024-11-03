<script lang="ts">

    import Download from "lucide-svelte/icons/download";
    import Users from "lucide-svelte/icons/users";

    import { Button } from "$lib/components/ui/button/index.js";
    import * as Card from "$lib/components/ui/card/index.js";
    import * as Tabs from "$lib/components/ui/tabs/index.js";
    import ProxiesTab from "./tab-proxies.svelte";
    import RelaysTab from "./tab-relays.svelte";
    import {CopyIcon, Save} from "lucide-svelte";
    import {Textarea} from "@/components/ui/textarea";
    import {Input} from "@/components/ui/input";

    const data = [
        {
            name: "storage",
            dataBalance: 500,
            price: 500,
            unit: 'sat',
        },
        {
            name: "upload",
            dataBalance: 500,
            price: 500,
            unit: 'sat',
        },
        {
            name: "download",
            dataBalance: 500,
            price: 500,
            unit: 'sat',
        }
    ]

</script>


<div class="flex-1 space-y-4 p-8 pt-6">
    <div class="flex items-center justify-between space-y-2">
        <h2 class="text-3xl font-bold tracking-tight">Balances</h2>
        <div class="flex items-center space-x-2">

        </div>
    </div>

    <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-7">

        <div class="grid md:grid-cols-1 col-span-4 gap-4">
            {#each data as row}
                <div class="bg-card text-card-foreground rounded-xl border shadow col-span-4">
                    <div class="flex flex-col space-y-1.5 p-6 pb-0">

                        <h1 class="font-semibold leading-none tracking-tight"><Save/>{row.name}</h1>
                    </div>

                    <div class="grid gap-4 md:grid-cols-2 lg:grid-cols-7 p-4">
                        <div class="flex bg-card text-card-foreground rounded-xl border shadow col-span-2 gap-2 p-2">
                            <p class="">{row.dataBalance}</p>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
        <div class="grid md:grid-cols-1 col-span-3 gap-4">
            <div class="bg-card text-card-foreground rounded-xl border shadow col-span-3">
                <div class="flex flex-col space-y-1.5 p-6 pb-0"><h3 class="font-semibold leading-none tracking-tight">Wallet</h3>
                    <p class="text-muted-foreground text-sm">Manage your funds</p></div>
                <div class="grid md:grid-cols-3 gap-2 p-4">

                    <div class="flex bg-card text-card-foreground rounded-xl border shadow col-span-1 gap-2 p-2">
                        <h1 class="">1 sat</h1>
                    </div>
                    <div class="grid md:grid-cols-3 col-span-2">
                        <div class="flex col-span-2 gap-2" >
                            <Input placeholder="cashuAeyJ0b2tlb..."></Input>
                        </div>
                        <div class="flex col-span-1 gap-2 pl-2">
                            <Button>Deposit</Button>
                        </div>
                        <div class="flex col-span-2 gap-2 pt-2" >
                            <Input placeholder="token will appear here..."></Input>
                        </div>
                        <div class="flex col-span-1 gap-2 pl-2 pt-2">
                            <Button >Withdraw</Button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="bg-card text-card-foreground rounded-xl border shadow col-span-3">
                <div class="flex flex-col space-y-1.5 p-6 pb-0"><h3 class="font-semibold leading-none tracking-tight">Proxy presets</h3>
                    <p class="text-muted-foreground text-sm">copy/paste some of these examples:</p></div>

                <div class="p-2">
                    <Button on:click={() => navigator.clipboard.writeText("wss://proxy.stens.dev")}><CopyIcon class="text-muted-foreground h-4 w-4" /></Button>wss://proxy.stens.dev
                </div>
                <div class="p-2">
                    <Button on:click={() => navigator.clipboard.writeText("wss://relay.damus.io")}><CopyIcon class="text-muted-foreground h-4 w-4" /></Button>wss://relay.damus.io
                </div>
                <div class="p-2">
                    <Button on:click={() => navigator.clipboard.writeText("ws://oxtrdevav64z64yb7x6rjg4ntzqjhedm5b5zjqulugknhzr46ny2qbad.onion")}><CopyIcon class="text-muted-foreground h-4 w-4" /></Button>Epoxy hzrd
                </div>
                <div class="p-2">

                    <Button on:click={() => navigator.clipboard.writeText("ws://437fqnfqtcaquzvs5sd43ugznw7dsoatvtskoowgnpn6q5vqkljcrsyd.onion/")}><CopyIcon class="text-muted-foreground h-4 w-4" /></Button>TOR Sattelite node
                </div>
                <div class="p-2">
                    <Button on:click={() => navigator.clipboard.writeText("6274e64ed65df73d8cdad414fbb67d9ae5d87579d8d4e1a2d19312fadbd23b3b")}><CopyIcon class="text-muted-foreground h-4 w-4" /></Button>Pubkey
                </div>
            </div>
        </div>
    </div>
    <!--{#if incomingEvents.length > 0}-->
    <!--    <div class="bg-card text-card-foreground rounded-xl border shadow">-->
    <!--        {#each incomingEvents as incomingEvent}-->
    <!--            <div class="bg-card text-card-foreground rounded-xl border shadow col-span-4 p-4">{incomingEvent}</div>-->
    <!--        {/each}-->
    <!--    </div>-->
    <!--{/if}-->

</div>