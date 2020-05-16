## App

    // required imports: @material-ui/core, @material-ui/styles
    // Need to create a Theme.js file

    // Theme.js file
    import { createMuiTheme } from '@material-ui/core/styles'

    export default createMuiTheme({

    })

    import React from 'react'
    import { ThemeProvider } from '@material-ui/core/styles'
    import theme from './ui/Theme'
    import Header from '../components/ui/Header'

    function App() {
        return (
            <ThemeProvider theme={theme}>
                <Header />
                Hello
            </ThemeProvider>
        )
    }

## Header

    // required imports: @material-ui/core

    import AppBar from '@material-ui/core/AppBar'
    import Toolbar from '@material-ui/core/Toolbar'
    import useScrollTrigger from '@material-ui/core/useScrollTrigger'

    function ElevationScroll(props) {
        const { children } = props

        const trigger = useScrollTrigger({
            disableHysteresis: true,
            threshold: 0,
        })

        return React.cloneElement(children, {
            elevation: trigger ? 4 : 0,
        })
    }

    export default function Header(props) {
        return (
            <ElevationScroll>
                <AppBar position='fixed'>
                    <Toolbar>Arc Development</Toolbar>
                </AppBar>
            </ElevationScroll>
        )
    }
