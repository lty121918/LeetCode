```
    async login(cb: Function, errCb: Function, showClose = true) {
        if (this.user) {
            console.warn("已在登录状态");
        }

        if (this.__openModal) return;
        this.__openModal = true;
        let defaultType = "wechat";
        function isMobilePhone() {
            //判断当前设备是手机
            const ua = navigator.userAgent.toLowerCase();
            const t1 = /android|webos|iphone|ipod|blackberry|iemobile|opera mini/i.test(
                ua
            );
            if (t1) {
                defaultType = "smsLogin";
            }
            return defaultType;
        }
        isMobilePhone();
        await AuthDialog.open({
            showClose,
            defaultType: defaultType,
            on: {
                success: (e: any) => {
```

```
        }
        &__desc {
            font-size: 12px;
            line-height: 20px;
            color: #ffffff;
        }
    }
}
@media screen and (max-width: 768px) {
    .g-auth {
        width: 100% !important;
        height: 390px !important;
    }
    .g-auth-login__form {
        padding: 0 50px !important;
    }
    .g-dialog__wrapper {
        top: auto !important;
    }
    .g-auth-register {
        padding: 0 65px !important;
    }
    .g-dialog {
        width: 100% !important;
        overflow: visible !important;
    }
    .g-auth-other-way-login__third-parties-content {
        display: none !important;
    }
    .g-auth-login .g-auth-login__links .g-btn {
        font-size: 14px !important;
    }
}
</style>
```

