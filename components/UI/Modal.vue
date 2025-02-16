<script lang="ts" setup>
interface ModalProps {
    isVisible: boolean
    size?: "default" | "s" | "m" | "l"
    bg?: "blur" | "colored"
    closeIcon?: boolean
}

const props = withDefaults(defineProps<ModalProps>(), {
    size: "default",
    bg: "blur",
    closeIcon: true,
})

const emits = defineEmits<{
    (e: "close"): void
}>()

const attrs = useAttrs()

const refModal = ref<HTMLDivElement>()
const hasScroll = ref(false)

const methods = {
    close() {
        emits("close")
    },
    overlayClick(e: MouseEvent) {
        if (!refModal.value?.contains(e.target as HTMLElement)) {
            methods.close()
        }
    },
    esc(e: KeyboardEvent) {
        if (e.code === "Escape") {
            methods.close()
        }
    },
}

watch(
    () => props.isVisible,
    (n) => {
        if (n) {
            document.addEventListener("keydown", methods.esc)
            nextTick(() => {
                const el = refModal.value?.querySelector(".slot")
                if (el) {
                    hasScroll.value = el?.scrollHeight > el?.clientHeight
                }
            })
        } else {
            document.removeEventListener("keydown", methods.esc)
        }
    },
)
</script>

<template>
    <Teleport
        v-bind="attrs"
        to="body"
    >
        <Transition name="fade">
            <div
                v-if="isVisible"
                v-bind="attrs"
                :class="['ui-modal', size, bg]"
                @mousedown.self="methods.overlayClick"
            >
                <Transition>
                    <div
                        ref="refModal"
                        class="modal-content"
                    >
                        <div
                            class="modal-close"
                            v-if="closeIcon"
                            @click="methods.close"
                        >
                            <span class="icon close"></span>
                        </div>

                        <div :class="['slot', { 'has-scroll': hasScroll }]">
                            <slot />
                        </div>
                    </div>
                </Transition>
            </div>
        </Transition>
    </Teleport>
</template>

<style lang="scss" scoped>
.ui-modal {
    box-sizing: border-box;
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1001;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 20px 10px;

    &.blur {
        background-color: rgba(62, 56, 75, 0.698);
        backdrop-filter: blur(7px);
    }

    &.colored {
        background-color: transparent;
        background-image: url("/images/login-bg.png");
        background-size: 100% 100%;
        background-repeat: no-repeat;
    }

    &.default {
        & > .modal-content {
            max-width: 460px;
        }
    }

    &.s {
        & > .modal-content {
            max-width: 437px;
        }
    }

    &.m {
        & > .modal-content {
            max-width: 648px;
        }
    }

    &.l {
        & > .modal-content {
            max-width: 785px;
        }
    }

    & > .modal-content {
        position: relative;
        width: 100%;
        max-height: 100%;
        padding: 48px 0;
        display: flex;
        flex-direction: column;
        background-color: white;
        border-radius: 15px;
        box-sizing: border-box;

        & > .modal-close {
            position: absolute;
            top: 0;
            right: -36px;
            width: 20px;
            height: 20px;
            cursor: pointer;

            & > .icon {
                background-color: white;
            }
        }

        & > .slot {
            overflow-x: hidden;
            overflow-y: auto;
            box-sizing: border-box;
            padding-right: 48px;
            padding-left: 48px;
            display: flex;
            flex-direction: column;
            gap: 24px;

            &.has-scroll {
                padding-right: 42px;
            }

            @-moz-document url-prefix() {
                scrollbar-width: thin;
                scrollbar-color: gray transparent;
            }

            &::-webkit-scrollbar {
                width: 6px;
            }

            &::-webkit-scrollbar-thumb {
                height: 10px;
                background-color: gray;
                border-radius: 10px;
            }
        }
    }
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.3s ease;
}

.fade-enter-active .modal-content,
.fade-leave-active .modal-content {
    transition: transform 0.3s ease;
}

.fade-leave-to {
    pointer-events: none;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

.fade-enter-from .modal-content,
.fade-leave-to .modal-content {
    transform: scale(0);
}

.fade-enter-to .modal-content,
.fade-leave-from .modal-content {
    transform: scale(1);
}
</style>
