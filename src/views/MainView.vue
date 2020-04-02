<template>
    <div>
        <HeaderCentered/>
        <CardsAligned/>
        <CalendarEvents/>
    </div>
</template>

<script>
    import HeaderCentered from '@/components/HeaderCentered';
    import CardsAligned from '@/components/CardsAligned';
    import CalendarEvents from '@/components/CalendarEvents';
    export default {
        components: {
            HeaderCentered,
            CardsAligned,
            CalendarEvents
        }
    }
</script>

<style lang="scss" scoped>

</style>