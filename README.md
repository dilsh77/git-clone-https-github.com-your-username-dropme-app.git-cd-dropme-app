# git-clone-https-github.com-your-username-dropme-app.git-cd-dropme-app
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
import { AuthProvider } from './src/context/AuthContext';

// Screens
import LoginScreen from './src/screens/Login/LoginScreen';
import UserDashboard from './src/screens/UserDashboard/UserDashboard';
import DriverDashboard from './src/screens/DriverDashboard/DriverDashboard';
import ServiceSelection from './src/screens/Services/ServiceSelection';
import RideBooking from './src/screens/Services/Ride/RideBooking';

const Stack = createNativeStackNavigator();

export default function App() {
  return (
    <AuthProvider>
      <NavigationContainer>
        <Stack.Navigator initialRouteName="Login">
          <Stack.Screen name="Login" component={LoginScreen} />
          <Stack.Screen name="UserDashboard" component={UserDashboard} />
          <Stack.Screen name="DriverDashboard" component={DriverDashboard} />
          <Stack.Screen name="Services" component={ServiceSelection} />
          <Stack.Screen name="RideBooking" component={RideBooking} />
        </Stack.Navigator>
      </NavigationContainer>
    </AuthProvider>
  );
}

