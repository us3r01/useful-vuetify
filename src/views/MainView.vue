<template>
    <div>
        <HeaderCentered/>
        <CardsAligned/>
        <CalendarEvents/>
        <EmbedSpotify/>
        <SignInCard/>
    </div>
</template>

<script>
    import HeaderCentered from '@/components/HeaderCentered';
    import CardsAligned from '@/components/CardsAligned';
    import CalendarEvents from '@/components/CalendarEvents';
    import EmbedSpotify from '@/components/EmbedSpotify';
    import SignInCard from '@/components/SignInCard';
    export default {
        components: {
            HeaderCentered,
            CardsAligned,
            CalendarEvents,
            EmbedSpotify,
            SignInCard
        }
    }
</script>

<style lang="scss" scoped>

</style>