console.clear()
const Express = require(`express`)()
const mysql = require(`mysql`)
const request = require(`request`)
const fs = require(`fs`)

function log(input) {
    if (input) console.log(`[Alt Bot]: ${input.toString()}`)
}


async function checkCookie(input) {
    const req = request.defaults()

    req.get({
        url: `https://roblox.com/mobileapi/userinfo`,
        headers: {
            "Cookie": `.ROBLOSECURITY=${input}`
        }
    }, (e, r, b) => {
        if (e) console.error(e)
        return (b.length < 250)
    })
}

async function getCookieInfo(input, callback) {
    var Valid = checkCookie(input)
    if (Valid) {
        const req = request.defaults()

        req.get({
            url: `https://roblox.com/mobileapi/userinfo`,
            headers: {
                "Cookie": `.ROBLOSECURITY=${input}`
            }
        }, (e, r, b) => {
            if (e) console.error(e)
            try {
                return callback(b)
            } catch (e) {
                console.error(e)
            }
        })
    } else {
        callback(null)
    }
}

async function getRandomArrayItem(input) {
    return input[Math.floor(Math.random() * input.length)]
}

async function fetchCookie() {
    var Data = JSON.parse(fs.readFileSync(`./cookies.json`))
    var fetchedCookie = getRandomArrayItem(Data)
    return fetchedCookie
}

async function getCookieAuth(input, callback) {
    if (checkCookie(input)) {
        const req = request.defaults()
        XSRF = req.post({
            url: `https://auth.roblox.com/v1/authentication-ticket`,
            headers: {
                "Cookie": `.ROBLOSECURITY=${input}`,
                "User-Agent": `Roblox/WinInet`,
                "Referer": 'https://www.roblox.com/develop',
                "RBX-For-Gameauth": 'true'
            }
        }, (e, r, b) => {
            if (e) console.error(e)
            req.post({
                url: `https://auth.roblox.com/v1/authentication-ticket`,
                headers: {
                    "Cookie": `.ROBLOSECURITY=${input}`,
                    "User-Agent": "Roblox/WinInet",
                    "Referer": "https://www.roblox.com/develop",
                    "RBX-For-Gameauth": "true",
                    "X-CSRF-TOKEN": r.headers['x-csrf-token']
                }
            }, (z, d, x) => {
                if (z) console.error(z)
                callback(d.headers['rbx-authentication-ticket'])
            })
        })
    } else {
        log(`Invalid cookie: '${input}'.`)
    }
}

async function checkGameId(input, callback) {
    const req = request.defaults()
    var result = req.get({
        url: `https://api.roblox.com/Marketplace/ProductInfo?assetId=${input}`
    }, async (e, r, b) => {
        if (e) console.error(e)
        if (b != null) {
            try {
                var Data = await JSON.parse(b)
                if (Data.Name) {
                    callback(true)
                } else {
                    callback(false)
                }
            } catch (e) {
                console.error(e)
            }
        } else {
            callback(false)
        }
    })
}

async function getCookieStatus(input, callback) {
    const req = request.defaults()
    var result = req.get({
        url: `http://api.roblox.com/users/${input}/onlinestatus`
    }, async (e, r, b) => {
        if (e) console.error(e)
        var Data = await JSON.parse(b)
        if (Data.LastLocation = "Offline") {
            callback(true)
        } else {
            callback(false)
        }
    })
}

Express.get(`/start`, async (req, res) => {
    try {
        var Cookie = ""
        var CookieIsValid = checkCookie(Cookie)
        if (CookieIsValid) {
            getCookieAuth(Cookie, (Authcode) => {
                var GameID = "123"
                var Time = Math.floor(+new Date())
                if (r[0].type == null) {
                    res.redirect(`roblox-player:1+launchmode:play+gameinfo:${}+launchtime:${}+placelauncherurl:https://assetgame.roblox.com/game/PlaceLauncher.ashx?request=RequestGame&browserTrackerId=60604189768&placeId=${}&isPlayTogetherGame=true+browsertrackerid:60604189768+robloxLocale:en_us+gameLocale:en_us`)
                } else {
                    res.redirect(`roblox-player:1+launchmode:play+gameinfo:${}+launchtime:${}+placelauncherurl:https://assetgame.roblox.com/game/PlaceLauncher.ashx?request=RequestGame&browserTrackerId=60604189768&placeId=${}&isPlayTogetherGame=${}+browsertrackerid:60604189768+robloxLocale:en_us+gameLocale:en_us`)
                }
            })
        } else {
            res.send(`<html><center>The randomly selected cookie is invalid!</center></html>`)
        }
    } catch (e) {
        if (e) console.error(e)
    }
})
Express.use((req, res) => {
    res.send(`The page you are looking for was not found or has no contents.`)
})

Express.listen(Config.Port, () => {
    log(`App started on port ${Config.Port}.`)
})
